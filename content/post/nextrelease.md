+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Next release of RsyncOSX."
tags = ["nextrelease"]
categories = ["changelog"]
description = "What is in next release of RsyncOSX?"
lastmod = "2020-06-30"
+++
Version 6.3.5 of RsyncOSX, release 30 June 2020. The following are enhancements in this release of RsyncOSX.

## SSH part

Others changes to the ssh part is only supporting rsa based creation of ssh keypair. The user can create a new key outside of RsyncOSX and just tell RsyncOSX where the new key is. The info about SSH keypath and identityfile must be [set in userconfig](/post/userconfiguration/).

![](/images/RsyncOSX/master/nextversion/globalssh.png)

A global ssh keypath and identityfile value can be overridden by a local set value. Also applies to SSH port number. Either global or local values are used.

![](/images/RsyncOSX/master/nextversion/localssh.png)

## Monitoring network connection

If enabling monitoring, RsyncOSX monitor the network connection on tasks with remote services. The monitoring is only valid during execution of the task. If there is discovered a network drop an interrupt signal is sent to the active task and it stops with an errormessage (in log).

macOS 10.14 or later
|---|
Monitoring network connection is only valid in macOS 10.14 or later.

In the user configuration ssh keypath, identity file, ssh port and select monitoring on/off are new options.

![](/images/RsyncOSX/master/nextversion/monitorandssh.png)

## New version of rsync

New version of rsync is released. RsyncOSX is verified working with latest version. It is advised to install [Homebrew](https://brew.sh/) and rsync as part of Homebrew.

![](/images/RsyncOSX/master/nextversion/newversionrsync.png)

## Main view in macOS 11

The top menus in RsyncOSX are slightly changed. I have an older Mac Book pro, 2016 model, which macOS 11 and Xcode 12 are installed on. I have also installed Homebrew (rsync, hugo and other tools), atom (the editor) and other applications on macOS 11. And they all works as expected. The old Mac might become my daily driver until macOS 11 is released.

Dark view in macOS Big Sur.

![](/images/RsyncOSX/master/nextversion/mainmacOS11.png)

Light view in macOS Big Sur.

![](/images/RsyncOSX/master/nextversion/mainmacOS112.png)

This is the current version in macOS Catalina.

![](/images/RsyncOSX/master/intro/main.png)
