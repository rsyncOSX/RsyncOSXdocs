---
layout: post
title:  "RcloneOSX changelog"
permalink: RcloneChangelog
---

Rclone is **rsync for cloud storage**. Even if `rclone` and `rsync` are somewhat equal they are also in many ways different. RcloneOSX is utilizing `rclone` for **synchronizing** and **backup** of files to a number of cloud services. RcloneOSX utilizes rclone copy, sync, move and check commands.

The app is signed with my Apple ID developer certificate and [notarized](/Notarized) by Apple.

## macOS Catalina

If you are installing on macOS Catalina, execute the `rclone` utility in a terminal window before using RcloneOSX. There is a process of granting access for the `rclone` utility before using it by RcloneOSX. MacOS Catalina will also ask permission for accessing your home catalog first time you start RcloneOSX.

## Development, bugfixes and coming versions of macOS

For the moment there is no active development of RcloneOSX. I will continue to compile, notarize and sign RcloneOSX for new versions of macOS and fix serious bugs. I will also refactor and enhance the code when required. But there will not be any new functions. My main effort in the future is to continue development of RsyncOSX and RsyncGUI.

## Version 2.1.5

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v2.1.5) 27 March 2020.

This is a "maintenance release". Batch is removed and replaced with multiple selection of tasks to execute.

## Version 2.1.1

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v2.1.1) 10 March 2020.

- fixed a bug in full restore

## Version 2.1.0

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v2.1.0) 9 March 2020.

Redesign of restore files, refactor of code and some bugfixes are the main objectives in this release.

## Version 2.0.6

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v2.0.6) 11 January 2020.

The release is **signed and notarized**.

- a few important bugfixes

## Version 2.0.5

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v2.0.5) 23 December 2019.

The release is **signed and notarized**. The major changes in the release are:

- maintenance release
- a few bugfixes

## Version 2.0.1

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v2.0.1) 9 November 2019.

The release is **signed and notarized**. The major changes in the release are:

- the restore part is refactored
- some other parts of code are refactored as well
- the copy single files are adjusted
- a few bugfixes

## Version 1.9.4

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.9.4) 4 October 2019. The release is **signed and notarized**. This version is built by Xcode 11 on macOS Catalina GM.

**Important** - from macOS 10.15 Catalina, [notarization is required](/Notarized) by default for all software.

- fixed a bug in copy files

## Version 1.9.3

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.9.3) 21 September 2019. The release is **signed and notarized**. This version is built by [Xcode 11)](https://developer.apple.com/documentation/xcode_release_notes/xcode_11_release_notes).

**Important** - from macOS 10.15 Catalina, [notarization is required](/Notarized) by default for all software.

- fixed a bug in delete logs

## Version 1.9.2

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.9.2) 14 September 2019. The release is **signed and notarized**. This version is built by [Xcode 11GM (Gold Master)](https://developer.apple.com/documentation/xcode_release_notes/xcode_11_release_notes).

**Important** - from macOS 10.15 Catalina, [notarization is required](/Notarized) by default for all software.

The major part (about 80%) in this version are refactor and cleanup in code. Refactor is mainly for decoupling of code and make RcloneOSX easier for maintenance.

- fixed a couple of memory leaks
- a few GUI adjustments
- fixed a bug in delete logs and save logs to permanent store
- some adjustments in search and sort (in logs and all profiles)
- refactor of code and cleanup

## Version 1.9.0

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.9.0) 13 June 2019.

- this is a maintenance release, some minor bugfixes and cleanup in code

## Version 1.8.1

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.8.1) 21 March 2019.

![](/images/RsyncOSX/master/nextversionrclone/nextversion.png)

- quit RcloneOSX by red button upper left main window
- view all profiles and configurations by menu button (moved from tab view)
- backup now and automatic backup my be executed from any view (tab) by menu buttons or shortcuts
- clean up of code, some minor bugfixes
- RcloneOSX center itself in screen when started
- configuration is available by shortcut `⌘,` (Preferences)

## Version 1.7.5

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.7.5) 10 February 2019.

Fixed a bug in  copy files.

## Version 1.7.1

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.7.1) 1 January 2019.

This is a maintenance release: cleanup in code and minor bugfixes.

## Version 1.7.0

[Released](https://github.com/rsyncOSX/rcloneosx/releases/tag/v1.7.0) 7 December 2018.

The **scheduling part is removed** from RcloneOSX. It was based upon an previous version of scheduling in [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX). The scheduling in RsyncOSX is moved to a [menu app](https://github.com/rsyncOSX/RsyncOSXsched) and I am not able to do so for the RcloneOSX. The scheduling was not working as it should in RcloneOSX and I don´t have time to develop it further. That is the main reason for removing it in RcloneOSX.

There is a new version 1.45 of rclone. If you are using version 1.45 of rclone you should download this version to get correct info about number of files to synchronize. There was a change in output from version 1.43 of rclone. This is set in userconfig of RcloneOSX.

- a lot of cleanup in code (delete of dead code)
- in user config tick of for `version 1.43 of rclone` for utilizing rclone versions => 1.43
- some enhancements in `restore`, restore defaults to temporary restore catalog if set
- estimating remote numbers and size are now included in quick backup
- fixed a bug in batch and some other bug fixes as well
- remove of scheduling

## Version 1.6.8

Relased 15 November 2018.

- minor bugfixes and tweaks

## Version 1.6.7

Relased 3 Nov 2018.

The following are changes in the release:
- enhanced quick sync tasks
- refactor batch tasks
- the userconfig is refactored
- and some minor bugfixes and tweaks
- the rcloneosx.app is [notarized](/Notarized) by Apple

Here are some screenshots of what is in [this version](/nextversionrclone).

## Version 1.6.5

Released 18 October 2018.

- rclone 1.44 is released
- copy files is redesigned
- some bugfixes as well

## Version 1.6.3

Released 29 September 2018.

- supports macOS Mojave and the new Dark Mode
- no logging, minimum or full logging enable/disable in user config
- version 1.43.1 of rclone is released
- bugfixes

## Version 1.6.0

Released 2 September 2018.

This is a maintenance release, the following changes are applied:

- bugfix due to a new version of rclone (version 1.43), the summary in output from rclone is slightly changed and a fix was required
- some other bugfixes as well
- added buttons and tooltips for tasks i main menu (top row)
- changed some of the icons for menu buttons
- refactor in parts of code

## Version 1.5.6

Released 16 August 2018.

- if task is selected in Synchronize view, only logs for selected task is presented in log view
- some enhancements in copy single files, fixed a memory leak
- implementing a new restore function from Synchronize view
- a new info view showing output from rclone during execution of single tasks

## Version 1.5.4

Released 21 June 2018.

- fixed a bug (crash) if RcloneOSX is started without installing rclone first
- some enhancements in [logs](/Logging) and caching of remote info

## Version 1.5.2

Released 1 July 2018.

- new app icon from [Zsolt Sándor](https://github.com/graphis)
- some refactor of code
- compiled with latest version of Xcode, version 9.4 (9F1027a)

## Version 1.5.1

Released 6 May 2018.


There are several enhancements in this release:
- `⌘I` gets remote info about tasks
- `⌘B` commence an automatic backup for `sync` tasks with data to sync
- selecting the i-button commence an estimating run for all `sync` tasks

## Version 1.4.0

- released 23 April 2018
- minor fix for enable restore of encrypted backups (see [encrypted](/Encrypted) backups in RsyncOSX)

## Version 1.3.6

- released 28 March 2018
- maintenance release, fixed a bug in schedules
- added a new new for all profiles
- added sort and filter in logs and all profiles

## Version 1.3.5

- released 6 March 2018
- refactor schedules
- cleanup of Synchronize view
- notification when scheduled tasks are completed

## Version 1.3.0

- released 23 January 2018
- some minor fixes

## Version 1.2.6

- released 9 January 2018
- a couple of minor bugfixes (logging)
- new function for quick backups, sort and select which tasks to be executed in one go
- sort and filter in **quick backups**

## Version 1.2.0

- v1.2.0 released 17 Dec 2017
- some bugfixes
- added scheduling of tasks

## Version 1.1.5

Scheduling tasks is disabled in this update. Schedules might be setup but it is not effective. Parts of the schedules needs refactor. Schedules will be enabled again when in next release.

- v1.1.5 is updated 10 Dec 2017
- focus on GUI single tasks and batch
- adding several shortcuts
	- after selecting a row the following shortcuts are effective
	- `⌘E` - shortcut for edit task
	- `⌘O` - shortcut for rclone parameters to task
	- `⌘D` - shortcut for delete task
	- `⌘R` - shortcut for immediate execute task, executing
	task by shortcut seems to be more effective compared execute by batch and single tasks
	- `⌘A` - Abort task

If a task is executed by shortcut `⌘R`, a select of another row during execution will terminate (abort) the current task. Scheduled task also might be aborted by selection the stop symbol.

## Version 1.1.1

- released 1 Dec 2017
- fixed a bug in batchview causing batch not executing properly

## Version 1.1.0

- released 28 Nov 2017
- new buttons are implemented
- fixed a typo and some minor fixes

## Version 1.0.0

- released 24 Nov 2017
- logging result after execution of tasks is fixed
- added possibility of logging, either minimum or full, output from rsync to loggfile in `Documents/rclonelog.txt`
	- the logging to file is default off when starting RcloneOSX, status of logging is not saved in userconfiguration
	- the log function appends new logs, be careful not logging all actions
- fixed some other minor glitches
- added number of days since last backup in Synchronize view

## version 0.2.5

* released 19 Nov 2017
* restore files and catalogs from cloud services
* minor bugfixes
* problem with logging is *probably* solved

## version 0.2.0

* new app icon and a few more bugfixes...
* enhancements in batchview

## Next version 0.1.5

* released 13 Nov 2017
* color rows in main table (`check` task in blue and `move` tasks in red)
* initial statistics and numbers are working
* only tasks `sync`, `copy` and `move` adding logs

## Version 0.0.3

* released 11 Nov 2017
* fixed a couple of bugs
* added command `check`
* only `sync`and `copy` tasks allowed executing in batch and by schedule
  - command `move` may cause some unwanted effects when executed, always do a `--dry-run` before executing
  - executing single tasks is always a two step task, first a `--dry-run` and then the real task after inspecting the result of the `--dry-run` task

## Version 0.0.2

* released 10 Nov 2017
* more fixes and enhancements, all commands as `copy`, `sync` and `move` are implemented
* still alfa release, but most functions work
* still work to do regarding numbers and statistics

## Version 0.0.1

By a couple of hours work with RcloneOSX I managed to do a `rclone copy` of a local directory to remote directory at Dropbox and Microsoft Onedrive. The Numbers part does not work yet because the output from `rclone` is quite different compared to `rsync`. Below are some screenshots from testing.

Adding cloud services is done by using the command line interface `rclone config`.

### What is working v0.0.1

* only `rclone copy`
  - verified with Dropbox and Microsoft Onedrive, expect others to work as well
* adding and executing single tasks
* batch tasks
* scheduled tasks
* logging tasks (only date, no numbers)
* profile, storing tasks in profiles
* change and delete configurations
* some parameters are working (just a few tests)

### What is not working v0.0.1

* numbers and statistics of transferred data
* for the moment only `rclone copy`
  - my knowlegde about rclone and its use is growing every day...
* no gui for `rclone config`
  - don't know if is possible to make a GUI for setting up rclone
  - for the moment investigating this issue is put on hold
