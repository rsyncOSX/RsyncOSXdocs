+++
author = "Thomas Evensen"
title = "Changelog"
date = "2021-04-23"
description = "Changelog"
tags = ["rsyncosx"]
categories = ["changelog"]
lastmod = "2021-03-24"
+++
If you are utilizing a local version of rsync, execute the rsync utility in a terminal window before using RsyncOSX. There is a process of granting access for the rsync utility before using it by RsyncOSX. MacOS will also ask permission for accessing your home catalog the first time you start RsyncOSX. If you also utilize the menu-app (RsyncOSXsched), be aware of you might have to force quit RsyncOSX the first time you start the menu-app. This is because the macOS asks for permissions when starting the menu-app for the first time and RsyncOSX is not closed automatically when starting the menu-app. This might happen only once first time start.

RsyncOSX is [signed and notarized](/post/notarized/). Please see info about [the latest version of rsync in install](/post/rsync/).

Using RsyncOSX requires some knowledge of `rsync`. The main objective for RsyncOSX is to ease the use of `rsync`, not teach macOS users how to use `rsync`. That is beyond the scope of RsyncOSX. Setting the wrong parameters to rsync can result in deleted data. And RsyncOSX will not stop you for doing so. That is why it is very important to execute a simulated run (`--dry-run`) and inspect what happens before a real run.

## Version 6.6.8 build (10) release candidate

Updated: 4 Nov 2021 - compiled on Apple Silicon (M1 Pro) by Xcode 13.1 as a Universal macOS Binary.

Build 9 -> 10 - fixed display correct profile in main view.

The updated version discover if you are on a Apple Silicon and enables the correct path for Homebrew if version 3 of rsync is ticked on.

There is some minor cleanup of GUI, but the **major work is internal**. There might be several hundred or thousands of log records. Reading and loading log records into memory is moved to when they are needed. And not when the app is started or a new profile is selected. The change will improve memory footprint and speed up the application.

## Version 6.6.7

Date: 22 September 2021

There are a couple of UI-fixes within this release. The release is also build by the Xcode 13 which was released yesterday.

## Version 6.6.5

Date: 18 September 2021

There is a bug for new users of RsyncOSX. The bug was related to creating log records after executing a task and also caused some unwanted sideeffects.

## Version 6.6.4 - issue sync remote task - fixed

Date: 11 September 2021

There is an issue with adding `syncremote` tasks in version 6.6.3. A syncremote task is pulling data from a remote server to local Mac.

The issue was caused only by a missing connection between a `@IBOutlet` variable and a `@IBAction` function. This is one of the drawbacks with storyboards. The connection must be established and somewhere during the cleanup of the UI the connection was dropped. And nothing was informing me about it was missing.

## Version 6.6.3

This build is for **macOS Big Sur and later**.

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.6.3) 25 July 2021.

This is a maintenance release with **one** bugfix and a **few** cleanups within the UI. The add view is cleaned up a little bit, profile info is moved to the sidebar.

## Version 6.6.2

This build is for **macOS Big Sur and later**.

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.6.2) 24 June 2021.

- fixed a bug in adding new configurations on a new install of RsyncOSX or creating a new profile

## Version 6.6.1

This build is for **macOS Big Sur and later**.

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.6.1) 21 June 2021.

This is primarly a maintenance release, some cleanup in code and fixing one "bug" when adding configurations. Default now when adding a configuration is adding trailing `/`. This was by mistake not in the 6.6.0 release. Adding a trailing `/` to rsync or not makes two very different tasks.

## Version 6.6.0

This build is for **macOS Big Sur and later**.

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.8) 6 June 2021

- the major work in this release is utilizing [Combine](/post/combine/)
- this release does only support macOS Big Sur and later versions of macOS (due to some features in Combine)

This release will be maintained in the future together with RsyncUI. Version 6.5.8 will still be available, but not maintaned. Integrating Combine into code and only supporting JSON does cleanup the code base for RsyncOSX. Less code is better code.

## Version 6.5.8

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.8) 24 March 2021

- there is fixed a bug in parameters to rsync, `-e ssh` is missing if there is **not** set an explicit ssh keypath and identityfile
- the above is only valid for remote servers, the parameter `-e ssh` causes the transferred data to be encrypted through a ssh tunell

## Version 6.5.7

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.7) 19 March 2021

- there are fixed a few layout (UI) issues in this release

## Version 6.5.6

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.6) 18 January 2021

There is a annoying bug in creating snapshots in version 6.5.4. It is one of the issues related to develop Swift and Storyboard applications. A button was removed in the Storyboard but not in code. And that one line of code causes a nil pointer exception and a crash.

- fixed a bug in creating new snapshot tasks
- some cleanup in Assist (in Add tasks) and some other parts

I am focusing on developing a SwiftUI based version of RsyncOSX and version 6.5.6 will probably be the last release for some time. Reported issues will be fixed (if bugs). There will most likely not be any further enhancements before the SwiftUI based version is released sometime in 2021.

## Version 6.5.4

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.4) 31 December 2020

The following is changed:

- there is a bug in deleting `snapshots`, please update if utilizing snapshots
- deleting snapshots is part of [administrating snapshots](/post/snapshots/)

## Version 6.5.3

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.3) 24 December 2020

The following are changes:

- application icon updated for Big Sur, by [Zsolt Sándor](https://github.com/graphis)
- Chinese (Simplified) localization updated, by [StringKe (Chen)](https://github.com/StringKe)
- a few minor bugfixes
- and several internal changes

In 2021 the main focus will be to develop a SwiftUI based version of RsyncOSX. And fix bugs when found. The internal updates in code is for the moment completed and any further updates will be as part of developing the SwiftUI based version.

I have no idea when a SwiftUI version wil be ready. I have a lot to learn about SwiftUI.

## Version 6.5.2

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.2) 4 December 2020

There are several internal changes in this version (refactor of code) to make the maintenance of the code more easy.

- there are a few changes to the main view, the main view is cleaned up and there is a new menubar on left side with the main actions for each view
- there are two new actions in main view, select a task and slide to left to execute, slide to right for delete
- the restore function is changed as well, there is now only possible to do restore, either full or file by file, to a temporary restore path
- there are fixed some minor bugs in the abort functions
- the bug in snapshot is fixed
- and there is some language updates as well

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

RsyncOSX supports read and write configurations and logs as [JSON](https://en.wikipedia.org/wiki/JSON) files.

There is an issue with **creating new** `snapshot` tasks in version 6.5.0. The bug is fixed in the release 6.5.2.

- create the snapshot task as usual
- in main view, select the task and [choose edit](/post/singletask/#edit-and-params)
- select `reset next snapshotnum` and set it to `1`, save the change that is it
- in main view there should be a `0` in column `snap`

## Version 6.4.6

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.6) 23 September 2020

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

Version 6.1.0 was released 24 December 2019. The initial relase was **14 March 2016**.
