+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Next release of RsyncOSX."
tags = ["nextrelease"]
categories = ["changelog"]
description = "What is in next release of RsyncOSX?"
lastmod = "2020-06-25"
+++
Next release of RsyncOSX
|---|
This release candidate is most likely to be the next release of RsyncOSX. There will probably be some more QA and cleanup in code, but there are no plans for new functionality. I will focus on next version of RsyncOSX and macOS 11 - Big Sur.

## SSH part

Others changes to the ssh part is only supporting rsa based creation of ssh keypair. The user can of course create a new key and just tell RsyncOSX where the new key is.

![](/images/RsyncOSX/master/nextversion/globalssh.png)

A global ssh keypath and identityfile value can be overridden by a local set value. Also applies to SSH port number. Either global er local values are used.

![](/images/RsyncOSX/master/nextversion/localssh.png)

## Monitoring network connection

If enabling monitoring, RsyncOSX monitor the network connection on tasks with remote services. The monitoring is only valid during execution of the task. If there is discovered a network drop an interrupt signal is sent to the active task and it stops with an errormessage (in log).

macOS 10.14 or later
|---|
Monitoring network connection is only valid in macOS 10.14 or later.

In the user configuration ssh keypath, identity file, ssh port and select monitoring on/off are new options.

![](/images/RsyncOSX/master/nextversion/monitorandssh.png)

## New version of rsync

New version of rsync is released. RsyncOSX is verified working with latest version.
![](/images/RsyncOSX/master/nextversion/newversionrsync.png)
