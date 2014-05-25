---
layout: post
tags: [android, firefox, mobile, mozilla, qa]
date: 2012-10-13 14:00:00
title: Testing H.264/AAC/MP3 decoding in Firefox Beta for Android
---

My last post on modifying an Android Stagefright H.264/AAC/MP3 decoder preference in Gecko, which toggles software and hardware decoding of  those formats in Firefox for Android briefly talked about how that override can be usful for testing. As part of our Firefox Beta testing cycle we want to extend our efforts in widening the degree of testing in leveraging the community for assistance in areas of testing different Android 4.0 (Ice Cream Sandwich) and Android 4.1 (Jelly Bean) based devics through different video based websites.

We could use your help testing but not limited to the following video and audio centric websites such as:

* [Grooveshark][] 
* [Bloomberg][]
* [FunnyOrDie][]
* [Dailymotion][]
* [Soundcloud][]

We are also looking for testing around different types of popular online video platforms where playback issues may exist. Recently, we have seen an issue where [Brightcove][] was identifying Firefox as unsupported due to a mismatch in the naming of profiles used in the list of supported video formats returned from the video.canPlayType() JS API. Their [player test-page](http://admin.brightcove.com/html5support/index.html) now currently identifies Firefox for Android as supported.

We are also seeking out any potential playback issues with Android devices. 

The following are example bugs related to devices of issues of which we have seen thus far:

* [Bug 785275][] - Galaxy S III hardware decoder shows green bars when playing non-720p videos (OMX_COLOR_FormatYUV420SemiPlanar)
* [Bug 797364][] - Stagefright: Galaxy SII & Galaxy Note hardware decoder video yields green layer over video
* [Bug 784329][] - No video playback on the Galaxy Nexus
* [Bug 783830][] - Playback on Samsung Galaxy SIII intercepted by AwesomePlayer
 
Currently, support is restricted to Ice Cream Sandwich and Jellybean devices with Gingerbread in development. The following devices are known to work and have been tested at Mozilla:

* HTC One X (Android 4.0)
* HTC One V (Android 4.0)
* Samsung Galaxy Note (Android 4.0)
* Samsung Galaxy Nexus (Android 4.0, 4.1)
* Samsung Galaxy SII (Android 4.0)
* Samsung Galaxy SIII (Android 4.0)
* Samsung Nexus S (Android 4.0, 4.1)

How to Help
-----------

-   First, we would like for you to download the new Firefox on Android
    (currently on the Beta channel) [available here] and install it
    onto your Android device

-   Try out different video-based websites that serve HTML5 video and audio, identify playback (player, audio, and video) issues

-   Create a Bugzilla account in our bug tracker so that you can file
    bugs you find against Firefox on Android in Bugzilla. Reminder,
    effective bug reports are likely to be fixed. There are excellent
    bug writing guidelines for your pleasure to read [here]
    
-   Join and chat with us on [Mozilla IRC](irc://irc.mozilla.org/QA) to talk with Mobile QA and mobile developers to let us know of any issues. We are particularily interested in the state of playback on other Android mobile devices and which sites work and which sites dont work

 [Bug 784329]: http://bugzil.la/784329
 [Bug 783830]: http://bugzil.la/783830
 [Bug 785275]: http://bugzil.la/785275
 [Bug 797364]: http://bugzil.la/797364
 [Grooveshark]: http://html5.grooveshark.com 
 [Bloomberg]: http://www.bloomberg.com
 [FunnyOrDie]: http://www.funnyordie.com
 [Dailymotion]: http://www.dailymotion.com
 [Soundcloud]: http://www.soundcloud.com
 [Brightcove]: http://www.brightcove.com
 [available here]: https://play.google.com/store/apps/details?id=org.mozilla.firefox_beta
 [here]: https://developer.mozilla.org/en/Bug_writing_guidelines