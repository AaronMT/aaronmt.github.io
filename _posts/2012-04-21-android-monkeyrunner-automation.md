---
layout: post
tags: [android, firefox, mobile, mozilla, qa]
date: 2012-04-21 20:42:00
title: Android MonkeyRunner Automation
---

A few folks have asked me what’s involved with my simple automation
script that ultimately produces screenshots of running browsers on
Android. It’s rather uncomplicated, I am using the [monkeyrunner][] tool
that is bundled with the [Android SDK.][] As the Android Developers
guide indicates:

> The monkeyrunner tool provides an API for writing programs that
> control an Android device or emulator from outside of Android code.
> With monkeyrunner, you can write a Python program that installs an
> Android application or test package, runs it, sends keystrokes to it,
> takes screenshots of its user interface, and stores screenshots on the
> workstation. The monkeyrunner tool is primarily designed to test
> applications and devices at the functional/framework level and for
> running unit test suites, but you are free to use it for other
> purposes.

Intended mainly as a tool for synthesizing input on Android, one can
also easily get a capture of the Android screen with its Python/Jython
API. The code below listens and connects to an Android device, loops
through a list of provided Android browser package/activities, visits a
site (provided by a CSV), waits a couple seconds for page-load (Hack!
How can I go about better doing this?), snaps a picture and writes it
out to a directory provided by argument.

    from com.android.monkeyrunner import MonkeyRunner, MonkeyDevice
    import sys, csv

    browsers = ['com.android.chrome/.Main',
                    'org.mozilla.fennec/.App']

    # Connects to the current device, returning a MonkeyDevice object
    device = MonkeyRunner.waitForConnection()

    #Start each browser activity with the provided URL
    for run, browser in enumerate(browsers):

        # Visit each site
        for visit, site in enumerate(csv.reader(open(sys.argv[1]).readlines())):

            # Start the activity with the provided site
            device.startActivity(component=browser, uri=site[0])

            # Wait for page load timeout        MonkeyRunner.sleep(20)

            # Snap a screenshot of the running activity
            device.takeSnapshot().writeToFile("%s%s-%s.png" % (sys.argv[2], visit, run), 'png')

  [monkeyrunner]: http://developer.android.com/guide/developing/tools/MonkeyRunner.html
  [Android SDK.]: http://developer.android.com/sdk/index.html