---
layout: post
tags: [android, firefox, mobile, mozilla, qa]
date: 2012-10-02 15:28:00
title: Mozilla Mobile QA (Firefox for Android) and AppThwack
---
Here at Mozilla, we’re always looking and investing in different ways
that our mobile related testing efforts and strategies can evolve and
expand into new avenues as Firefox for Android mature as a product.
We’re always engaged in seeking out different yet worthwhile services
and tools that can integrate into our regular QA process.

Whilst we continue to operate as a small team (Mobile QA for Firefox on
Android is about two-full time employees); we’re seeking all the help we
can get whether it be from [community][] or from those who have created
[services][] and [utilities][] to assist mobile QA efforts.

We react in seeking solutions by continuing to identify and respond to
problems. In identifying our areas of contention, we still see [Android
device fragmentation][] and access on-demand to [Android devices][] as
major paint-points of Android testing. To administer any type of soluton
would involve boasting and utilizing the services and assistance from
others. Currently we use DeviceAnywhere for one-off direct device
testing; but we desired a service that targets automation.  

A couple months ago we stumbled upon [AppThwack][], a service that
manages mobile application and fragmentation issues by deploying
uploaded [Android Package (APK)][] files and deploying (installation) on
**real**Android based phones and tablets. The devices are hosted and
interfaced through web front-end that makes it easy to view and extract
results ran from automated tests (currently self-written and
provided [MonkeyRunner][] tests are available, and on-track towards
deploying [Robotium][] and *possibly in the near future* Mozilla based
[Robocop][] tests). Alongside, screen-shots are provided from multiple
device orientations which make it usful for identifying any
user-interface issues. A test-run takes a couple minutes and any data
collected may be bundled and downloaded together to deploy towards any
new Bugzilla bug for track-keeping.

Currently, we are utilizing their service for testing Firefox for
Android builds during our [rapid release Beta cycle][] and are looking
at different strategies of integration for the other channels within our
cycle.

If you would like to see what a test-run looks like [click here][].

  [community]: https://wiki.mozilla.org/QA/Fennec/Armv6Compatibility#Unofficial_Community-Driven_Device_Testing_Table
  [services]: http://www.keynotedeviceanywhere.com
  [utilities]: http://testdroid.com
  [Android device fragmentation]: http://developer.android.com/about/dashboards/index.html
  [Android devices]: http://www.android.com/devices/
  [AppThwack]: http://www.appthwack.com
  [Android Package (APK)]: http://en.wikipedia.org/wiki/APK_(file_format)
  [MonkeyRunner]: http://developer.android.com/tools/help/monkeyrunner_concepts.html
  [Robotium]: http://code.google.com/p/robotium/
  [Robocop]: https://wiki.mozilla.org/Auto-tools/Projects/Robocop
  [rapid release Beta cycle]: https://wiki.mozilla.org/RapidRelease/Calendar
  [click here]: http://www.appthwack.com/public/WrPWGZz58L