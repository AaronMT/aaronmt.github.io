---
layout: post
title: "Language Switching in Fennec"
description: ""
category: 
tags: []
---

[As Jeff Beatty describes][1], language switching in [Nightly][2] is now available. Ultimately, this linguistic enhancement allows one to select from _all officially shipped localizations_ from within the browser independent from available language selection provided by Android. As Jeff calls out, "Languages no longer have to be among the list of Android supported languages to become official localizations of the browser."

Firefox for Android QA is looking for help from others for discovering issues found when trying this feature out.

The developer of the feature, [Richard Newman][4], calls out the following to look for in [Bug 917480][3] when testing this feature on Nightly:

Note: the option to control this is in *Menu > Settings > Language > Browser language*

* Nightly should obey one's selection as their preferred Android system-provided language. Firefox has obeyed this in previous and current releases

* Nightly should use one one of the languages we ship, regardless of system language

* Testing this feature involves verifying that a change is immediately applied, and that all entry points into the application reflect the selected language

* Entry points to check:
-- Data reporting notification. This launches Settings in the "Mozilla" section. Titles should be correct: on tablet, for example, you should see "Settings" in the top left, and "Mozilla" as a heading. You only get this on first run, so you'll need to Clear Data to get back to a clean slate and test this out
-- Launching the browser. Top sites should be in the correct language, as well as other UI elements
-- Clicking a link from another application
-- Installable [Firefox Market][5] Web applications

Other areas affected by language change:

* Sync settings when accessed via Nightly and via Android Settings > Accounts & Sync > Firefox

* Sent tabs from other devices: the launched notification should be in the last language you picked

Notes of interest:

* Language selection changes should be persistent across browser sessions and restarts

* All chrome content, such as error pages should be in the correct selected language

* Setting the browser language has the side effect of changing your Accept-Language header. You should get pages in non-phone languages sometimes; depends on the site

* Verify that switching to Android Settings and changing the system language does the right thing if "System default" is selected, and does the different right thing if a specific language is selected

If you discover any issues, [please file a bug on Bugzilla][6]

References:

[Bug 917480][3]

Try it out on [Nightly][2] today

[1]: https://blog.mozilla.org/l10n/2014/05/20/language-switching-in-fennec/
[2]: http://nightly.mozilla.org
[3]: https://bugzilla.mozilla.org/show_bug.cgi?id=917480
[4]: https://twitter.com/rnewman
[5]: https://marketplace.firefox.com
[6]: https://bugzilla.mozilla.org/enter_bug.cgi?product=Firefox%20for%20Android&component=Locale%20switching%20and%20selection 