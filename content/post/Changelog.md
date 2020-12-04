+++
author = "RsyncOSX"
title = "The RsyncOSX changelog"
date = "2020-04-23"
description = "Changelog"
tags = ["rsyncosx"]
categories = ["changelog"]
lastmod = "2020-10-23"
+++
[![GitHub license](https://img.shields.io/github/license/rsyncOSX/RsyncOSX)](https://github.com/rsyncOSX/RsyncOSX/blob/master/Licence.MD) ![GitHub Releases](https://img.shields.io/github/downloads/rsyncosx/RsyncOSX/v6.5.0/total) ![GitHub Releases](https://img.shields.io/github/downloads/rsyncosx/RsyncOSX/v6.4.6/total) [![Crowdin](https://badges.crowdin.net/rsyncosx/localized.svg)](https://crowdin.com/project/rsyncosx) [![Netlify Status](https://api.netlify.com/api/v1/badges/d375f6d7-dc9f-4913-ab43-bfd46d172eb2/deploy-status)](https://app.netlify.com/sites/rsyncosx/deploys) [![GitHub issues](https://img.shields.io/github/issues/rsyncOSX/RsyncOSX)](https://github.com/rsyncOSX/RsyncOSX/issues)

If you are installing on macOS Catalina or macOS Big Sur and utilize a local version of rsync, execute the rsync utility in a terminal window before using RsyncOSX. There is a process of granting access for the rsync utility before using it by RsyncOSX. MacOS Catalina or macOS Big Sur will also ask permission for accessing your home catalog first time you start RsyncOSX.

If you also utilize the menu-app (RsyncOSXsched), be aware of you might have to force quit RsyncOSX the first time you start the menu-app. This is because the macOS Catalina and macOS Big Sur ask for permissions when starting the menu-app for the first time and RsyncOSX is not closed automatically when starting the menu-app. This might happen only once first time start.

All releases of RsyncOSX are [signed and notarized](/post/notarized/). Please see info about [the latest version of rsync in install](/post/rsync/). All versions are built as [Universal macOS Binary](https://developer.apple.com/documentation/xcode/building_a_universal_macos_binary).

## Version 6.5.2

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.0) 4 December 2020

This released is **not** announced. If there are no errors reported in the next few weeks this release will be the next release.

There are several internal changes in this release (refactor of code) to make the maintenance of the code more easy. The app is compiled as a [Universal macOS Binary](https://developer.apple.com/documentation/xcode/building_a_universal_macos_binary).

There are a few changes to [the main view](/post/new) in this release. The main view is cleaned up and there is a new menubar on left side with the main actions foe each view.

The restore function is changed as well. There is now only possible to do restore, either full or file by file, to a temporary restore path.

And there are fixed some minor bugs in the abort functions.

And the bug in snapshot is fixed.

## Workaround snapshot in version 6.5.0

There is an issue with **creating new** `snapshot` tasks in version 6.5.0. The bug is fixed in the release 6.5.2.

- create the snapshot task as usual
- in main view, select the task and [choose edit](/post/singletask/#edit-and-params)
- select `reset next snapshotnum` and set it to `1`, save the change that is it
- in main view there should be a `0` in column `snap`

There are also some minor issues utilizing the shortcuts like copy (`⌘C`) and paste(`⌘V`) values from commandline into like the Add configurations. It is fixed now. And there is a cleanup within the `Assist` function as well.

## Version 6.5.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.0) 12 November 2020

Version 6.5.0 and later versions are only working on macOS 10.15 Catalina and 11.01 Big Sur. This version is built om macOS Big Sur with Xcode 12.2.

- a new [Assist function](/post/addconfigurations/#assist)
- language updates (Chinese, German, Norwegian and Dutch)
- fixed a bug within the ssh function, thx to [Paul Dee](https://github.com/systemcrash) for [reporting the bug](https://github.com/rsyncOSX/RsyncOSX/issues/1956), the crash is caused by a bug if the ssh public key is not present in the ssh keypath catalog
- there is also fixed a minor glitch in the menu app, in default profile the schedules was not presented in the main view
- backup of configurations and logs (in [userconfig](/post/userconfiguration/))
- several internal changes (refactor) in code
- the [check function](/post/check/) is moved to the File menu
- and some minor fixes in the menu app

RsyncOSX supports read and write configurations and logs as [JSON](https://en.wikipedia.org/wiki/JSON) files:

- see more [info about json](/post/json/)

Before trying out JSON convert existing PLIST configurations to JSON format (⌘J). If you try out the JSON format and want to return to PLIST, do a backup, transform existing JSON format to PLIST and return to PLIST in userconfig. Also, [in userconfig](/post/userconfiguration/), do a backup of existing configurations.

## Version 6.4.6

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.6) 23 September 2020

**RsyncOSX is compiled with support for macOS 10.15 Catalina and 11.00 Big Sur.**

The following are changes in the release:

-  default path for RsyncOSX config files is changed to `$HOME/.rsyncosx/macserialnumber`
	- existing users can choose to migrate or keep config files in previous default path which is `$HOME/Documents/Rsync/macserialnumber`
	- in About the used path for config files is presented
- the Restore part is adjusted
- and a few minor fixes
- due to the above issue, RsyncOSX version 6.4.6 and later is for macOS 10.15 and later

The reason for changing path for config file is there might be some issues for users utilizing primary store for `$HOME/Documents` catalog in iCloud. Storing config files at new path is more reliable. RsyncOSX can move config files for you. In File menu choose `Move config` and follow the instructions. The old config files are saved within the Documents catalog.

## Version 6.4.2

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.2) 22 August 2020

- fixed some bugs in logs and schedule part
- fixed issue when creating a snapshot task
- adding a snapshot task with remote server require to be online with server, the validate function check if online or not
- a lot of internal fixes and cleanup of old code
- the Add view is cleaned

## Version 6.4.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.0) 26 July 2020

There is one major enhancement in the release, execute shell scripts before and after the rsync command. A serious bug in dates and the menu app is also fixed. And lastly there is also fixed a bug in deleting and canceling schedules.

Pre and post shell scripts are **only executed** by selecting the task and by `⌘B` (Execute now, RsyncOSX) or by a schedule in the menu app (RsyncOSXsched).

- adding execute post and pre scripts on tasks (requested by [@Dante Barba](https://github.com/dantebarba))
	- by [utilizing John Sundell´s ShellOut](https://github.com/JohnSundell/ShellOut)
	- shell scripts may be used for mounting and unmounting volumes before and after rsync task or any other housekeeping tasks
	- add and enable, disable pre and post shell commands in Add or Edit view
- the menu app (RsyncOSXsched) now executes pre and post scripts
- fixed bug in canceling and deleting schedules
- fixed a serious bug how dates are calculated in both RsyncOSX and the menu app (reported by [@CaspervdGeer](https://github.com/CaspervdGeer))
- QA and updates of old code, some of the old code needs update

## Version 6.3.5

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.3.5) 30 June 2020

- some localization updates (German, Chinese Simplified, French)
- added user set SSH keypath and identityfile, global and local settings
- refactor of RsyncOSX support SSH keypair creation
- enabled monitoring if drop in network connection during execution of tasks (only valid in macOS 10.14 and higher)

## Version 6.3.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.3.0) 26 May 2020

- added counting numbers in quick backup
- updatet a more precise counting when rsync is transferring files
- added clean logfile in view output from rsync
- some minor fixes and cleanups

## Version 6.2.6

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.2.6) 23 April 2020.

- batch is removed and replaced with multiple selection of tasks to execute
- Italian localization added
- clean up of GUIs and code
- refactor of the Restore part
- updated the GUI of menu app (for executing scheduled tasks)
- logging rsync errors to file
- added set ssh identity file (normally either id_dsa or id_rsa)
- added copy output from rsync to macOS clipboard

## Version 6.2.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.2.0) 27 February 2020.

- restore single files and the full restore are combined
- cleaned up some other views as well
- cleaned (refactor) up some code

## Version 6.1.7

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.1.7) 5 February 2020.

There are a few minor changes and enhancements in this release. The most noticeable change is the possibility to select another profile direct from the main, schedule and snapshot view (not from the profile dropdown menu). There are also some other minor changes which improves the usability of RsyncOSX. localization are updated as well.

## Version 6.1.5

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.1.5) 11 January 2020.

- added German and French localization
- fixed a minor bug
- added input control in add configurations
- some GUI changes due to new localization

## Version 6.1.0 - initial release

Version 6.1.0 was released 24 December 2019. The initial relase was 14 March 2016.
