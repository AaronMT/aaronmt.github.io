---
layout: post
title: "Profiling Gecko in Firefox for Android"
description: ""
category: 
tags: []
---

At last week's [Mozilla QA Meetup][1] in Mountain View, California I demonstrated how to effectively profile Gecko in Firefox for Android on a device. By targeting a device running Firefox for Android, one can measure responsiveness and performance costs of executed code in Gecko. By measuring sample set intervals, we can focus on a snapshot of a stack and pinpoint functions and application resources produced by a sampling run. With this knowledge, one can provide a valuable sampling of information back to developers to better filed bug reports. Typically, as we have seen, these are helpful in bug reports for measuring page-load and scrolling and panning performance problems, frame performance and other GPU issues.

How to Help
-------------

* Install this ([available here][2]) Gecko Profiler add-on in Firefox on your desktop (it is the Gecko profiler used for platform execution), and follow the [instructions outlined here][3] for setting up an environment
* If you encounter odd slowdown in Firefox for Android, profile it! You can save the profile locally or share it via URL
* Add it to a (or your) bug report on [Bugzilla][7]
* Talk to us on [IRC][6] about your experience or problems

Here is an example bug report, [bug 1047127][5] (panning stutters on a page with overflow-x) where a profile may prove helpful for further investigation.

Detailed information on profiling in general is available on MDN [here][4].

[1]: http://www.meetup.com/The-Mountain-View-Mozilla-Meetup-Group/events/194226832/
[2]: https://addons.mozilla.org/en-US/firefox/addon/gecko-profiler/?src=api
[3]: https://developer.mozilla.org/en-US/docs/Mozilla/Performance/Profiling_with_the_Built-in_Profiler#Profiling_Firefox_mobile
[4]: https://developer.mozilla.org/en-US/docs/Mozilla/Performance/Profiling_with_the_Built-in_Profiler
[5]: https://bugzilla.mozilla.org/show_bug.cgi?id=1047127
[6]: irc://irc.mozilla.org/mobile
[7]: https://bugzilla.mozilla.org/enter_bug.cgi?product=Firefox%20for%20Android