+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2020-07-05"
+++
RsyncOSX is [released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.3.5) in version 6.3.5 (30 June 2020). It is not required to install the menu app (RsyncOSXsched.app). The menu app is for executing [scheduled tasks](/post/scheduletasks) only.

RsyncOSX is [signed and notarized](/post/notarized/). There is a short [intro](/post/intro/) to RsyncOSX.

## Install

The command

`shasum ~/pathtodownload/RsyncOSX-version.dmg`

will print the shasum for the .dmg file. For your own safety verify the shasums.
```
RsyncOSX 6.3.5.dmg: 538c2284ec8831c6fcb2adb7183942cc3b95e6a2
RsyncOSXsched 6.3.5.dmg: 08e2e1cac31b027ca2644f8e91e59547858f0d95
```
To install RsyncOSX open the downloaded RsyncOSX-version.dmg file, copy the RsyncOSX.app to the `/Application` catalog or any other preferred catalog. And likewise for the RsyncOSXsched-version.dmg.

RsyncOSX is installed and used at your own risk. The developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Version 3.1.3 of rsync

See readme.txt within dmg file for how to manually install version rsync 3.1.3.
```
rsync313.dmg: 568ccf4d0981223f51e1c54941bc6cbc87988ae8
```

## Latest version of rsync

See more info about [the latest version of rsync and how to install it](/post/rsync/).

## Passwordless logins

Utilizing RsyncOSX for synchronize files and backup to remote servers require to setup [passwordless logins to remote servers](/post/remotelogins/).
