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
- Create a PlayReady, Widevine, Primetime and Marlin CENC encrypted MPEG-DASH manifest and files using Bento4 packager. 

- Provides single-encryption workflow for playback on:

  - Desktops
  - Android 4.3+
  - Windows Phone
  - Chromecast
  - Android TV
  - Google TV
  - Roku
  - Amazon Fire TV
  - Samsung Smart TV & Tizen TV
  - Smart TV Alliance (LG, Philips, Toshiba, Panasonic) 
  - TNT (2.0+) Specification
  - HbbTV (1.5+) Specification
  - Xbox One / 360
  - PlayStation 3 / 4


--------------------------------
 Apple HLS 
--------------------------------
.. Above is the document title, and below is the subtitle.
.. They are transformed from section titles after parsing.
- Create FairPlay (SAMPLE-AES) encrypted HLS manifest and files using Bento4 for playback with Safari HTML5 on Mac OSX, iOS apps, and Apple TV apps.



================================
 ExpressPlay Cloud Secure Key Manager 
================================

ExpressPlay provides secure online storage service for your content cryptographic keys * at no additional charge *. The ExpressPlay Key Storage Service uses the Simple Key Management (SKM) REST API, that allows the packager and adaptive player to push/pull content keys to/from ExpressPlay. 

================================
 Amazon AWS Cloudfront Private Distributions
================================
- Once DRM-enabled DASH and HLS packages are complete, upload to Amazon S3 for AWS CloudFront distribution.  

  - The S3 bucket is configured with restricted access, limited to CloudFront Origin Access Identity and Authorized AWS User.
  - CORS is configured restricting access to your player's domain.
  - AWS CloudFront (CF) is configured for Web delivery, (optional) CNAME and SSL SNI, S3 bucket restrictions and Origin Access Identity, Cache Behaviour policies and Geo restriction policies.  

================================
 HTML5 Player
================================
Bitdash HTML5 Javascript Player version 4+.

Bitdash enables HTML5 adaptive streaming with MPEG-DASH native in your browser with no need for plugins like Flash or Silverlight. Due to the native integration with the browser it is possible to play back very high resolutions such as 4K or very high framerates like 60fps.

Encrypted HTML5 based adaptive streaming with MPEG-DASH native in your browser without plugins. Multiple DRM systems, e.g., PlayReady and Widevine can be used in parallel through MPEG Common Encryption (MPEG-CENC). Google Chrome is currently removing Silverlight, so PlayReady will not be supported anymore. bitdash provides a solution with MPEG-CENC your content will be encrypted once and can be used with different DRM systems in parallel.


