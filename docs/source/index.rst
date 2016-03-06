.. DataPlastic Content Protection documentation master file, created by
.. sphinx-quickstart on Fri Feb 19 12:04:26 2016.
.. You can adapt this file completely to your liking, but it should at least
.. contain the root `toctree` directive.
.. Widevine Modular DRM native in Google Chrome 35+, Opera (31+), Android 4.3+.
.. PlayReady DRM native in Internet Explorer (11+ on Windows 8.1+), Microsoft Edge (Windows 10+), Windows Phone (8.1+), Microsoft Surface.
.. FairPlay Streaming DRM native in iOS, Safari on OSX, AppleTV. Supports AirPlay.

We design for DRM & Content Protection (DRMCP) plug-in free playback solutions using desktop and mobile HTML5 rendered multi-DRM encrypted video.

Our DRMCP content authoring workflow approach is tailored to use encrypt-once common encryption (CENC) using HTML5 EME and CDM to manage end-user playback.



.. contents:: Table of Contents
.. section-numbering::



---------


DRM
==========================================================
Depending on the appropriate playback protection device use-case, integrate with Intertrust's ExpressPlay and Secure Key Manager or AWS Cloudfront content protection mechanisms.

For Adobe Primetime DRM (Firefox 43+ CDM support), the Bento4 CENC packager supports Primetime encryption for DASH, however neither the Bitdash player nor ExpressPlay support Primetime DRM at this time.  



================================
 ExpressPlay Cloud DRM
================================

Secure, cloud-based content protection system from the inventor of DRM. Provide single API access for multi-DRM support.
ExpressPlay is a cloud-based DRM service provider for content protection across most consumer-used devices. Enable your online media service with robust rights management without the need for any new infrastructure or setup cost.

The following adaptive bit rate streams are supported by a single HTML5 Javascript player installation, Bitdash 4.0+. 

.. Note:: MPEG-DASH.
- DESKTOP MPEG-DASH

  + Protected with Widevine Modular, Microsoft PlayReady, Fairplay, and Marlin DRM
  * Native Google Widevine HTML5 MSE Browser Support

    - Google Chrome 35+
    - Opera (31+)
    - Android 4.3+
   
    
  * Native Microsoft PlayReady HTML5 MSE Browser Support

    - Internet Explorer (11+ on Windows 8.1+)
    - Microsoft Edge (Windows 10+) 
 
   
  * Native Apple FairPlay HTML5 MSE Browser Support

    - Safari 8+ on Mac OSX.
    
  * Native Adobe Primetime HTML5 MSE Browser Support [Coming Soon]

    - Firefox (38+) on Windows
    

- DESKTOP HLS

  + Protected with AES-128 encryption and Widevine DRM
  
  * Native AES HTML5 Browser Support

    - Microsoft Edge (Windows 10+) 
  
   
    
  * Native Widevine HTML5 Browser Support


    - Android 4.3+ 
 


---------

+------------------------+------------+----------+----------+
| Header row, column 1   | Header 2   | Header 3 | Header 4 |
| (header rows optional) |            |          |          |
+========================+============+==========+==========+
| body row 1, column 1   | column 2   | column 3 | column 4 |
+------------------------+------------+----------+----------+
| body row 2             | Cells may span columns.          |
+------------------------+------------+---------------------+
| body row 3             | Cells may  | - Table cells       |
+------------------------+ span rows. | - contain           |
| body row 4             |            | - body elements.    |
+------------------------+------------+----------+----------+
| body row 5             | Cells may also be     |          |
|                        | empty: ``-->``        |          |
+------------------------+-----------------------+----------+

--------------------------------
 MPEG-DASH
--------------------------------
.. Above is the document title, and below is the subtitle.
.. They are transformed from section titles after parsing.
- Create a PlayReady, Widevine, Primetime and Marlin CENC encrypted MPEG-DASH manifest and files using Bento4 packager. 



--------------------------------
 Apple HLS 
--------------------------------
.. Above is the document title, and below is the subtitle.
.. They are transformed from section titles after parsing.
- Create FairPlay (SAMPLE-AES) encrypted HLS manifest and files using Bento4 for playback with Safari HTML5 on Mac OSX, iOS apps, and Apple TV apps.



--------------------------------
 ExpressPlay Cloud Simple Key Manager (SKM)
--------------------------------

ExpressPlay provides secure online storage service for your content cryptographic keys * at no additional charge *. The ExpressPlay Key Storage Service uses the Simple Key Management (SKM) REST API, that allows the packager and adaptive player to push/pull content keys to/from ExpressPlay. 

Each DASH or HLS packaging process requests the creation of new SKM Key Object prior to multi-DRM CENC encryption. The cloud stored keys are used as inputs to provide encryption data to the manifests.



--------------------------------
 Amazon AWS Cloudfront Private Distributions
--------------------------------
- Once DRM-enabled DASH and HLS packages are complete, upload to Amazon S3 for AWS CloudFront distribution.  

  - The S3 bucket is configured with restricted access, limited to CloudFront Origin Access Identity and Authorized AWS User.
  - CORS is configured restricting access to your player's domain.
  - AWS CloudFront (CF) is configured for Web delivery, (optional) CNAME and SSL SNI, S3 bucket restrictions and Origin Access Identity, Cache Behaviour policies and Geo restriction policies.  


                
 ================================
Ingest and DRM packaging process
================================

We use Bento4, a C++ class library and tools designed to read and write ISO-MP4 files. This format is defined in international specifications ISO/IEC 14496-12, 14496-14 and 14496-15. The format is a derivative of the Apple Quicktime file format.

MPEG DASH with fragmented MP4 files, as defined in the international specification ISO/IEC 23009-1
MPEG Common Encryption (CENC) as specified in the international specification ISO/IEC 23001-7

Supports multiple DRM systems that are compatible with MP4-formatted content (leveraging CENC Common Encryption), such as Marlin, PlayReady, Widevine and FairPlay.
Support for a wide range of codecs, including H.264 (AVC), H.265 (HEVC), AAC, AC3 and eAC3 (Dolby Digital), DTS, ALAC.


.. sidebar:: Sidebar Title
:subtitle: Optional Subtitle
 

   .. rubric:: This is a rubric inside a sidebar

   Sidebars often appears beside the main text with a border and
   background color.

.. topic:: Topic Title

   This is a topic.
   
   
 .. figure:: https://api.dataplastic.com/demo/package_master_file.jpg
:alt: reStructuredText, the markup syntax

   A figure is an image with a caption and/or a legend:

   +------------+-----------------------------------------------+
   | re         | Revised, revisited, based on 're' module.     |
   +------------+-----------------------------------------------+
   | Structured | Structure-enhanced text, structuredtext.      |
   +------------+-----------------------------------------------+
   | Text       | Well it is, isn't it?                         |
   +------------+-----------------------------------------------+


1.	We provide SFTP account details to upload source/mezzanine content to our packagers, including your metadata, your transcoding configuration and AWS credentials in a JSON file. This file contains supplied packaging directives (eg resolutions for multi-bitrates, info on multi-language support in audio tracks etc).
2.	We transcode source to AVC and HEVC renditions based on the JSON configuration file. MP4 (H.264) files are converted to HEVC (H.265), encoded using MulticoreWare X.265 libraries.
3.	The H.264 and H.265 files are then fragmented. For existing Microsoft Smooth ISMV and ISMA input files, these are refragmented into compliant fragmented MP4 files.
4.	Packaging 
 I.	Convert MP4 files to an MPEG DASH presentation, consisting of an initial XML manfifest, called the Media Presentation Document (MPD for short), which describes media segments that form a complete presentation. Along with a number of attributes, the MPD allows the MPEG DASH player to compute the URL of each segment, to download it and render it.
 II.	Convert MP4 files to an HLS (HTTP Live Streaming) presentation, including the generation of the segments and .m3u8 playlist as well as AES-128 and SAMPLE-AES (for Fairplay DRM) encryption.

Prior to adaptive presentation generation, the packager requests a new Key Object from ExpressPlay SKM API that creates unique cryptographic keys in the cloud for use in the packaging for each adaptive asset presentation. 
The fragmented MP4 files are then converted to DASH and HLS presentations, encrypted with Common Encryption mode (CENC). Widevine, PlayReady and Marlin encryption keys are embedded in DASH manifests, and FairPlay DRM in HLS manifests. 

5. We transfer encrypted packages to your Amazon S3 bucket using AWS Signature Version 4 API signing process, enabling S3’s server-side AES256 encryption by default. 

================================
 HTML5 Player
================================
Bitdash HTML5 Javascript Player version 4+.

Bitdash enables HTML5 adaptive streaming with MPEG-DASH native in your browser with no need for plugins like Flash or Silverlight. Due to the native integration with the browser it is possible to play back very high resolutions such as 4K or very high framerates like 60fps.

Encrypted HTML5 based adaptive streaming with MPEG-DASH native in your browser without plugins. Multiple DRM systems, e.g., PlayReady and Widevine can be used in parallel through MPEG Common Encryption (MPEG-CENC). Google Chrome is currently removing Silverlight, so PlayReady will not be supported anymore. bitdash provides a solution with MPEG-CENC your content will be encrypted once and can be used with different DRM systems in parallel.


The following player code snippet is representative of the rights managed data dynamically loaded by the video player.

.. compound::

 source: {
            dash                    : <MPD URI>,
            
            hls                     : <m3u8 URI>,
            
            progressive             : <MP4 URI>?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9zZWN1cmUuZGF0YXBsYXN0aWMuY29tL1RPU0RBU0gvbXA0L1RvU18zNjBwLm1wNCIsIkNvbmRpdGlvbiI6eyJJcEFkZHJlc3MiOnsiQVdTOlNvdXJjZUlwIjoiMTE1LjE4Ny4yMzYuMTcwLzEifSwiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE0NTY0ODE4MjZ9fX1dfQ==&Signature=kQfYiRNkk5U0Unx8QEDRk2wvUWRschkJcLZGq6g0adL5YnIV9wVyadwf2GhpIna85V3M8Td246eErET6SqkRN6C7koc8ChvHGNhxQCZ7KxwOWW9~fi7d82wppNVKIOHaxqZvTatqXdaHheQ7TS92qgaD4iAnA7lASela9gDKjxvoGLBUeQDLtTVYuXY3Ps2XG4TTNRSC1wtZSZqRnAuuo60AcEX9SuAlhzRcUWODZ4t58qggfqlK-0-yFCqj2rSi8SXukB3oO5N6WtunUdpqfZlstRTJ9tX6k9xVjGLomjEclIu03wdJ4IrbONkSh9lS~V7QNjtgZtv69tYHvxusrg__&Key-Pair-Id=9999999999
            


widevine or playready             : 

                    LA_URL              : <ExpressPlay Token URI>/?ExpressPlayToken=AQAAAAbTKGIAAABQK2Nll44xo95DwyFp9Rcb1snIRwiJaLINE4WSg-Je1MaSMRF6QIx2lV_bPX5qY77Hu2V5xaWYL-SqBuZyR93TKW6tf1piINl2zVryFdAL0ZfJIGjepZb1kTFb6oEB0YDpGgVFGA


