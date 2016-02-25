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

For Adobe Primetime DRM (Firefox 43+ CDM support), the Bento4 CENC packager supports Primetime encryption for DASH, however neither the Bitdash player nor ExpressPlay support Primetime DRM at this time (in development).  



================================
 ExpressPlay Cloud DRM
================================

Secure, cloud-based content protection system from the inventor of DRM. Provide single API access for multi-DRM support.
ExpressPlay is a cloud-based DRM service provider for content protection across most consumer-used devices. Enable your online media service with robust rights management without the need for any new infrastructure or setup cost.

The following adaptive bit rate streams are supported by a single HTML5 Javascript player installation, Bitdash 4.0+. 

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
    
  * Native Adobe Primetime HTML5 MSE Browser Support

    - Firefox (38+) on Windows
    
- DESKTOP HLS

  + Protected with AES-128 encryption and Widevine DRM
  
  * Native AES HTML5 Browser Support

    - Microsoft Edge (Windows 10+) 
  
   
    
  * Native Widevine HTML5 Browser Support


    - Android 4.3+ 
 


---------


--------------------------------
 MPEG-DASH
--------------------------------
.. Above is the document title, and below is the subtitle.
.. They are transformed from section titles after parsing.
- Create a PlayReady, Widevine and Marlin CENC encrypted MPEG-DASH manifest using Bento4 packager.

- Fragment all the MP4 video renditions to be packed into DASH.
- In the packaging script, the sequence is as follows..
  + Generates a unique Encryption Key (EK).
  + Creates a new key SKM object, passing ContentID in API request.
  + Consumes the API response KID, .
  

- Item 2.
--------------------------------
 Apple HLS 
--------------------------------
.. Above is the document title, and below is the subtitle.
.. They are transformed from section titles after parsing.
Create FairPlay (SAMPLE-AES) encrypted HLS using Bento4.


.. Attention:: Directives at large.
--------------------------------
 Progressive Download
--------------------------------
.. Above is the document title, and below is the subtitle.
..They are transformed from section titles after parsing.

---------

================================
 ExpressPlay Cloud Secure Key Manager (SKM)
================================

The purpose of the SKM API is to provide a very simple interface for software and services that need a simple and convenient way to store and/or retrieve cryptographic keys. This includes content packagers, head-end scramblers, DRM license servers, etc.
ExpressPlay offers an optional secure online storage service for your content keys * at no additional charge *. The ExpressPlay Key Storage Service uses the Simple Key Management (SKM) API, a simple REST API that allows you to push/pull content keys to/from ExpressPlay. 

================================
 Amazon AWS Cloudfront Private Distributions
================================

================================
 HTML5 Player
================================
Bitdash


About Document
==========================================================

This document system dynamically builds content markup based on GitHub commits. Each content commit fires an event that dynamically builds the web content, unattended.

.. bibliographic fields (which also require a transform):

:Author:
:Address: 123 Example Street
          Example, EX  Canada
          A1B 2C3
:Contact: docutils-develop@lists.sourceforge.net
:Authors: Me; Myself; I
:organization: humankind
:date: $Date: 2012-01-03 19:23:53 +0000 (Tue, 03 Jan 2012) $
:status: This is a "work in progress"
:revision: $Revision: 7302 $
:version: 1
:copyright: This document has been placed in the public domain. You
                may do with it as you wish. You may copy, modify,
                redistribute, reattribute, sell, buy, rent, lease,
                destroy, or improve it, quote it at length, excerpt,
                incorporate, collate, fold, staple, or mutilate it, or do
                anything else to it that your or anyone else's heart
                desires.
:field name: This is a generic bibliographic field.
:field name 2:
        Generic bibliographic fields may contain multiple body elements.

        Like this.

:Dedication:

        For Docutils users & co-developers.

:abstract:

        This document is a demonstration of the reStructuredText markup
        language, containing examples of all basic reStructuredText
        constructs and many advanced constructs.

.. meta::
:keywords: reStructuredText, demonstration, demo, parser
   :description lang=en: A demonstration of the reStructuredText
           markup language, containing examples of all basic
           constructs and many advanced constructs.


