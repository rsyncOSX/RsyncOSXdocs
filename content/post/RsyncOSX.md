+++
author = "RsyncOSX"
date = 2020-04-23T09:34:29+02:00
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2020-06-30"
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
To install RsyncOSX open the downloaded RsyncOSX-version.dmg file, copy the RsyncOSX.app to the /Application catalog or any other preferred catalog. And likewise for the RsyncOSXsched-version.dmg.

RsyncOSX is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Version 3.2.1 of rsync

Version 3.2.1 of rsync
|---|
If you experience problems with rsync 3.2.1 caused by missing libraries, please use version 3.1.3. Or install rsync as part of Homebrew (recommended).

See readme.txt within dmg file for how to manually install version rsync 3.2.1.
```
rsync321.dmg: 559b4e48b3531896a8bfa51d37ec5c579a1ffb41
rsync313.dmg: 568ccf4d0981223f51e1c54941bc6cbc87988ae8
```

## Versions of rsync

The default version of rsync in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version 2.6.9 was released in nov 2006. The current release of rsync is version [3.2.1](https://download.samba.org/pub/rsync/NEWS) protocol 31 released 22 June 2020. Version 3.2.1 of rsync is bundled together with RsyncOSX. It is strongly recommended to install rsync as part of Homebrew if other version than default version in macOS.

- install [homebrew](https://brew.sh/) and install the latest version of rsync as part of homebrew (`brew install rsync`)
- get rsync-3.2.1.dmg from [releases](https://github.com/rsyncOSX/RsyncOSX/releases) to install version 3.2.1 of rsync

In RsyncOSX select [user configuration](/post/userconfiguration/) and set path for optional version of rsync.

## Passwordless logins

Using RsyncOSX for backup to remote servers require to setup [passwordless logins to remote servers](/post/remotelogins/).
