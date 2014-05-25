---
layout: post
tags: [mobile, mozilla, qa, fxos]
date: 2012-11-26 23:00:00
title: Dabbling with Marionette and Gaia UI layer testing 
---

Over the last few weeks in-between [Firefox for Android][] release cycle work, I have been bestowed on the interests of contributing to the [Gaia][] UI automation efforts established from the Mozilla Web QA and Automation & Tools teams by assisting in writing, extending and building upon the available tests and APIs. Preliminary development of an extensive test suite of basic functional [smoke-tests][] tests is underway.

Reviewing the available [Gaia][] [smoke-tests][], the feasible test-cases can be written into Python based manifest-driven tests that are executed by Mozilla's own automation driver, [Marionette][]. Sharing much of the same API as [Selenium and Web Driver], it makes writing tests rather easy. For example, a [first test I have written recently](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/tests/test_music.py) is able to launch, interact and assert content behaviors of HTML elements in the bundled [Gaia music application](https://github.com/mozilla-b2g/gaia/tree/master/apps/music) with relative ease — afterall, each application is merely HTML.

Each test that is built upon the [Marionette][] foundation utilizes a Python package named [Gaiatest][] (available on PyPi [here](http://pypi.python.org/pypi/gaiatest/0.3)) that is in-fact based on [Marionette][]. It is used specifically for writing tests against [Gaia][] and has a growing variety of atomic [Gaia][] related APIs such as: [unlocking the device home-screen](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/atoms/gaia_lock_screen.js), [toggling WiFi/cellular data](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/atoms/gaia_data_layer.js), [setting volume](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/atoms/gaia_data_layer.js) and interactions with other device settings, etc. For example, here is the current [data_layer.js](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/atoms/gaia_data_layer.js) file where we can write functions that interact with accessible public interfaces from the variety of available [WebAPI]. In turn we can we abstract and create APIs for use in our tests (e.g, preliminary tests such as [test_dialer.py](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/tests/test_dialer.py) disables device volume and soon to be [test_browser.py](https://github.com/mozilla/gaia-ui-tests/blob/master/gaiatest/tests/test_browser.py) where one can toggle WiFi and or celluar data).

I would encourage all those who are currently writing Gaia applications to try out [Marionette][] and [Gaiatest][] and to contribute to our UI automation efforts by writing well-tested tests to expand our current test-suite. The [Github][] repository is where all activity is at with chatter taking place on #appsqa on Mozilla IRC. 

Further information on running [Marionette][] tests can be read [here](https://developer.mozilla.org/en-US/docs/Marionette/Running_Tests) alongside a [README](https://github.com/mozilla/gaia-ui-tests/blob/master/README.md) for installing and setting up [Gaiatest][].

 [Firefox for Android]: https://wiki.mozilla.org/RapidRelease/Calendar
 [Gaia]: https://wiki.mozilla.org/Gaia
 [Gaiatest]: https://github.com/mozilla/gaia-ui-tests
 [Marionette]: https://developer.mozilla.org/en-US/docs/Marionette
 [Selenium and Web Driver]: http://code.google.com/p/selenium/wiki/JsonWireProtocol
 [Smoke-tests]: https://etherpad.mozilla.org/smoketest-tests
 [WebAPI]: https://wiki.mozilla.org/WebAPI