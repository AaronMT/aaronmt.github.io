---
layout: post
tags: [android, firefox, mobile, mozilla, qa]
date: 2012-06-30 19:46:00
title: Destroy all the activities!
---

These past few days, an [influx][] [of][] [reports][] [have][]
[arrived][] with users reporting that the new Firefox on Android will
’*ultimately* *fail to properly load web-pages’*as strongly convened
from investigating the multiple reports.

Turns out for whatever reason folks seem to be enabling a tucked away
Android 4.0 (Ice Cream Sandwich) developer option — ’**Don’t keep
activities**’ with the description:
’**<span style="text-decoration: underline;">Destroy</span>**
**<span style="text-decoration: underline;">every</span>**
**<span style="text-decoration: underline;">activity</span>** as soon as
the user leaves it’, which means that Gecko is likely killed when a user
tries to visit a URL from the browser’s ‘Awesome Screen’.

As Kevin Brosnan points out in our tracking **[bug 769269][],**



It is a nice find and an interesting case. Moral of the story please
keep this developer option disabled to prevent destruction of *all* the
activities! 

  [influx]: https://support.mozilla.org/en-US/questions/931141
  [of]: https://support.mozilla.org/en-US/questions/931056
  [reports]: https://support.mozilla.org/en-US/questions/930825
  [have]: https://support.mozilla.org/en-US/questions/931107
  [arrived]: https://bugzilla.mozilla.org/show_bug.cgi?id=769269
  [bug 769269]: http://bugzil.la/769269
  []: /storage/dev-opt-1.png?__SQUARESPACE_CACHEVERSION=1341103986261