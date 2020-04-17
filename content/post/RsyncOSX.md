---
layout: post
title:  "Install RsyncOSX"
permalink: Install
---
RsyncOSX is [released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.2.0) in version 6.2.0 (27 February 2020). It is **not** required to install the [RsyncOSXsched.app](https://github.com/rsyncOSX/RsyncOSXsched). RsyncOSXsched.app is for scheduled tasks only.

RsyncOSX is [signed and notarized](/Notarized). There is a short [intro](/Intro) to RsyncOSX.

### Install RsyncOSX.app and  RsyncOSXsched.app

The command `shasum ~/pathtodownload/RsyncOSX-version.dmg` will print the shasum for the .dmg file. For your own safety verify the shasums.

- RsyncOSX-6.2.0.dmg: 7afafa77f48f39effb9e97cd2cb2f2117be4bfee
- RsyncOSXsched-6.2.0.dmg: 64d9262a179f1ec7fdfde05aba6720105e74b4af

To install RsyncOSX open the downloaded `RsyncOSX-version.dmg` file, copy the RsyncOSX.app to the `/Application` catalog or any other preferred catalog. And likewise for the `RsyncOSXsched-version.dmg`.

RsyncOSX is installed and used at your own risk and developer accepts no responsibility for any errors, omissions or loss of data by using the application.

### Version 3.1.3 of rsync

See readme.txt within dmg file for how to manually install version rsync 3.1.3.

- rsync313.dmg: 568ccf4d0981223f51e1c54941bc6cbc87988ae8

## Versions of rsync

The default version of `rsync` in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) protocol 31 released 28 January 2018. There are at least three options to get and install the current version of rsync for use in RsyncOSX:

- install [homebrew](https://en.wikipedia.org/wiki/Homebrew_(package_management_software)) and then install rsync as part of homebrew
- get `rsync-3.1.3.dmg` from [releases](https://github.com/rsyncOSX/RsyncOSX/releases) to install the latest version of rsync
- install Xcode and download the rsync [source](https://rsync.samba.org/) from rsync.samba.org
	- required tools are `gcc` and `make` which are part of Xcode command line tool (you might be able to install Xcode command line tool only by downloading the tools from [Apple Developer page](https://developer.apple.com/))
	- untar the [source archive](https://download.samba.org/pub/rsync/src/) and use `make` to compile and install, rsync compiles without any issues on macOS


In RsyncOSX select [user configuration](/UserConfiguration) and set path for optional version of rsync.

## Passwordless logins to remote servers

Using RsyncOSX for backup to **remote servers** require [passwordless logins to remote servers](/Remotelogins).
