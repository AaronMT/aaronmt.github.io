---
layout: post
title: "Firefox for Android   UI Testing (Robocop) Update"
description: ""
category: 
tags: [mobile, mozilla, qa, android, firefox]
---

[_For more information on Robocop Automation, see this [Mozilla Wiki entry](https://wiki.mozilla.org/Auto-tools/Projects/Robocop)_]

Short update of where we (Mozilla QA) are at with our recent automation efforts in converting our smoke-tests to automated tests. As of this month there are now approximately [forty-five](http://mxr.mozilla.org/mozilla-central/source/mobile/android/base/tests/) available Mochitest-Robotium (Robocop) tests with approximately thirty currently enabled and running per-checkin ([_see example run here_](https://tbpl.mozilla.org/php/getParsedLog.php?id=19850040&tree=Firefox)). Each individual test is ran (see [Firefox - Tinderbox Pushlog](https://tbpl.mozilla.org/)) in-part of a growing suite of automated user-interface tests that exercise in probing and injecting various native events to the Java front-end of Firefox for Android. In-turn, these provide automation for our list of identified browser [smoke-tests](https://moztrap.mozilla.org) (manual testing). While we have steady progress henceforth, we are always looking for more interested to-be test-authors who wish to help us continue to grow our automation efforts. 

Short summary on some of the blocking situations we have recently ran into and some details on their solutions:

* Due to a number of user-interface differences between various Android devices, it was deemed necessary to create a Device and Navigation support class in [BaseTest](http://mxr.mozilla.org/mozilla-central/source/mobile/android/base/tests/BaseTest.java.in). Further investigation revealed that was it also necessary to map navigation (Back, Forward and Reload) due to different types of Android devices (i.e, tablets vs phones and varying Android platform versions) _see [bug 747835](http://bugzil.la/747835)_.

* Test stablization on the Panda and Tegra boards has been tricky. After further investigation we found out that the Tegra boards run Android 2.3 (API Level 11), and Firefox for Android serves the small-screen mobile user-interface for phones running Android 2.3. The Panda boards run Android 4.0.4 (API Level 15) and Firefox for Android serve the larger-screen mobile user-intreface optimized for 7-inch tablets running Android 4.0+. This split environment was rather sub-optimal.

* On Android 3.0+ (API Level 12+), the system Cancel and Ok buttons were switched around (gee, thanks Google!) so it was deemed necessary to use a clickOnButton(name); function instead of clickOnButton(index);. This was causing some failures early on.

* Again on Android 3.0+ (API Level 12+) pop-up notification buttons were not accessible at times due in part to the to an invocation of the system virtual keyboard, which would overlay cover the testable view. This was a result of having prior, entering text via the sendKeys() function. Thus this requires dismissing the virtual keyboard first and foremost before trying to click any buttons _see ongoing investigation in [bug 838596](http://bugzil.la/838596)_.

* Depending on the Android device, platform and screen-size we have varying user-interfaces thus it was required to check for proper navigation depending on the environemtn (e.g, we have a function to check for the "More" and "Tools" submenus in order to access items), _see [bug 830755](http://bugzil.la/830755)_.

* We had to hack around finding a solution for traversing the number of views in Firefox for Android's settings user-interface. In detail, we had to dynamically fetch the number of checkboxes available to ensure that if further items are to be added, these will not affect the running test. This requires disecting the settings menu and asserting if each component is a checkbox, _see ongoing investigation in [bug 830834](http://bugzil.la/830834)_.

## Current work and areas we need help in
* Expanding our set of tests, [_see existing coverage here_](https://docs.google.com/spreadsheet/ccc?key=0AhE7m4JB2j6tdDJBT2dlbVJwUk9PSy1RbHo4WVNiUGc#gid=8)
* Stabilize set of problematic tests (intermittent failures and timeouts), _see mozilla-central's [test manifest](http://mxr.mozilla.org/mozilla-central/source/mobile/android/base/tests/robocop.ini); specifically, [bug 825152](https://bugzilla.mozilla.org/show_bug.cgi?id=825152), [bug 746876](https://bugzilla.mozilla.org/show_bug.cgi?id=746876), [bug 824067](https://bugzilla.mozilla.org/show_bug.cgi?id=824067), [813107](https://bugzilla.mozilla.org/show_bug.cgi?id=813107), [bug 757475](https://bugzilla.mozilla.org/show_bug.cgi?id=757475), [bug 738890](https://bugzilla.mozilla.org/show_bug.cgi?id=738890)

## How you can help
* Run our [manual set of smoke-tests](https://moztrap.mozilla.org/manage/cases/?filter-suite=8) against [Nightly](http://nightly.mozilla.org) builds of Firefox on your Android phone or tablet
* Contribute towards writing additional tests (see: [writing Robocop tests](https://wiki.mozilla.org/Auto-tools/Projects/Robocop/WritingTests)); individual tests are tagged as either automatable or not in Moztrap
* Contribute towards improving the Robocop framework (see: [Auto-tools](https://wiki.mozilla.org/Auto-tools#Want_to_Help.3F)); see [open Robocop related bugs](http://goo.gl/vUX8f), [source code](http://hg.mozilla.org/mozilla-central/file/148ea95584b4/build/mobile/robocop)