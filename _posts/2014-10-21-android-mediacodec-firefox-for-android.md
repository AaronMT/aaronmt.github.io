---
layout: post
title: "Android MediaCodec use in Firefox for Android"
description: ""
category: 
tags: []
---

[James 'snorp' Willcox][1] has [landed support][2] for software & hardware decoding via the [MediaCodec][3] Java API in [Nightly][4] for Android for devices running Android 4.1+ (Jellybean). This is replacing OMXCodec & the Stagefright library which was introduced as a replacement for OpenCore for media decoding. This relatively new public Java class is used for decoding H.264/AAC in MP4 for playback in the browser with the benefit of allowing for direct access to the media codecs on the device through a "raw" interface. 

This should correct a number of playback issues which have been reported to us regarding problems on Android 4.1+ devices.

[Victory!][5]

How to Help
-------------

* Install [Nightly][4] (available on 10/21/2014's build)
* Test video playback on your Android 4.1+ device (e.g, [test page][6])
* Talk to us on [IRC][7] about your experience or problems

[1]: https://github.com/snorp
[2]: https://bugzilla.mozilla.org/show_bug.cgi?id=1014614
[3]: http://developer.android.com/reference/android/media/MediaCodec.html
[4]: http://nightly.mozilla.org
[5]: https://bugzilla.mozilla.org/show_bug.cgi?id=1014614#c78
[6]: http://people.mozilla.org/~atrain/mobile/tests/media.html
[7]: irc://irc.mozilla.org/mobile