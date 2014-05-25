---
layout: post
tags: [android, firefox, mobile, mozilla, qa]
date: 2012-09-12 15:14:00
title: Debug preference for testing H.264/MPEG-4 AVC in Firefox for Android
---

[Nightly][] for Android has recently adapted a new
[about:config][] preference for using and more-so testing Android
H.264/MPEG-4 AVC decoding. The preference
is media.stagefright.omxcodec.flags

Utimately, this preference allows one to override whether Firefox uses
Android’s H.264/MPEG-4 AVC software or hardware decoder. As Chris
Peterson mentions in the same [announcement][], this is useful for
debugging different configurations and conveinent for testing.

Flags values to note:

 

-   0 - Android will use either hardware or software decoding
    (**default**)
-   8 - Force software decoding
-   16 - Force hardware decoding

 

Reference: [OMXCodec::CreationFlags][]

  [Nightly]: http://nightly.mozilla.org
  [about:config]: http://kb.mozillazine.org/About:config
  [announcement]: https://groups.google.com/forum/?fromgroups#!topic/mozilla.dev.platforms.mobile/KgkqfFb_ISA
  [OMXCodec::CreationFlags]: https://github.com/android/platform_frameworks_base/blob/ics-plus-aosp/include/media/stagefright/OMXCodec.h#L35