---
layout: post
title: "Proxy Server Testing in Firefox for Android"
description: ""
category: 
tags: []
---

Recent work on standing up a proxy server for web browsing in Firefox for Android is now ready for real world testing. [Eugen][1], [Sylvain][2], and [James][3], from the mobile platform team have been working towards the goal of building a proxy server to ultimately increase privacy (via a secure connection), reduce bandwidth usage, and improve latency. Reduced page load times is also a high level goal. A detailed Wiki page is available at: [https://wiki.mozilla.org/Mobile/Janus][4]

The time for testing is now.

How to Help
-------------

* Install this ([available here][5]) proxy configuration (development server) add-on in Firefox for Android
* Browse as you normally would (try your network connection and or WiFi connections)
* [File bugs in GitHub][6] (make sure to compare with the proxy enabled and disabled)
* Talk to us on [IRC][7]

[1]: https://github.com/eamsen
[2]: https://github.com/Ackar
[3]: https://github.com/snorp
[4]: https://wiki.mozilla.org/Mobile/Janus
[5]: https://github.com/mozilla/janus-addon/raw/master/janus.xpi
[6]: https://github.com/mozilla/node-janus/issues
[7]: irc://irc.mozilla.org/mobile