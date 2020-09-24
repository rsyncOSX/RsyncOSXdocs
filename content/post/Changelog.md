+++
author = "RsyncOSX"
title = "The RsyncOSX changelog"
date = "2020-04-23"
description = "Changelog"
tags = ["rsyncosx"]
categories = ["changelog"]
lastmod = "2020-09-01"
+++
If you are installing on macOS Catalina or macOS Big Sur and utilize a local version of rsync, execute the rsync utility in a terminal window before using RsyncOSX. There is a process of granting access for the rsync utility before using it by RsyncOSX. MacOS Catalina or macOS Big Sur will also ask permission for accessing your home catalog first time you start RsyncOSX.

If you also utilize the menu-app (RsyncOSXsched), be aware of you might have to force quit RsyncOSX the first time you start the menu-app. This is because the macOS Catalina and macOS Big Sur ask for permissions when starting the menu-app for the first time and RsyncOSX is not closed automatically when starting the menu-app. This might happen only once first time start.

All releases of RsyncOSX are [signed and notarized](/post/notarized/). See info about [the latest version of rsync in install](/post/rsync/).

## Version 6.4.6

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.6) 23 September 2020

**Caution: version 6.4.2, 6.4.6 and later versions are only working on macOS 10.15 Catalina and 11.00 Big Sur**, [please see this issue](https://github.com/rsyncOSX/RsyncOSX/issues/1949).

The following are changes in the release:

-  default path for RsyncOSX config files is changed to `$HOME/.rsyncosx/macserialnumber`
	- existing users can choose to migrate or keep config files in previous default path which is `$HOME/Documents/Rsync/macserialnumber`
	- in About the used path for config files is presented
- the Restore part is adjusted
- and a few minor fixes
- due to the above issue, RsyncOSX version 6.4.6 and later is for macOS 10.15 and later

The reason for changing path for config file is there might be some issues for users utilizing primary store for `$HOME/Documents` catalog in iCloud. Storing config files at new path is more reliable. RsyncOSX can move config files for you, in File menu choose `Move config` and follow the instructions. The old config files are saved within the Documents catalog.

![](/images/RsyncOSX/master/rclone/menu.png)

The used path can be viewed in About. New path after move is `$HOME/.rsyncosx/macserialnumber`.

![](/images/RsyncOSX/master/rclone/about.png)

## Version 6.4.2

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.2) 22 August 2020

**Caution: version 6.4.2, 6.4.6 and later versions are only working on macOS 10.15 Catalina and 11.00 Big Sur**, [please see this issue](https://github.com/rsyncOSX/RsyncOSX/issues/1949).

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

## Version 6.1.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.1.0) 24 December 2019.

- added new type of task syncremote
- added possibility to remove the trailing / when adding tasks, if you remove the trailing / be sure you understand what it means
- added parameter to set $date on backup folder
- refactor of schedule
- check of schedule logs
- minimized GUI of the menu app

If you have any suggestions for enhancements or if you discover bugs, [please report an issue](https://github.com/rsyncOSX/RsyncOSX/issues).

## Version 6.0.1

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.0.1) 10 November 2019.

- refactor of restore (the restore view is now a tabview)
- some adjustments in Copy Files
- some adjustments in administration of Snapshots
- further refactor and cleanup in code
- update of Chinese translation (and some updates in the Norwegian translation as well)

## Version 5.9.4

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.9.3) 8 October 2019

The only changes compared to 5.9.3 is this version is built on release macOS Catalina by Xcode 11.1. MacOS Catalina and Xcode 11.1 was released 7 Oct 2019.

## Version 5.9.3

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.9.3) 12 September 2019. The release is **signed and notarized**. This version is built by [Xcode 11GM (Gold Master)](https://developer.apple.com/documentation/xcode_release_notes/xcode_11_release_notes).

**Important** - from macOS 10.15 Catalina, [notarization is required](/post/notarized/) by default for all software.

The major part (about 80%) in this version are refactor and cleanup in code. Refactor is mainly for decoupling of code and make RsyncOSX easier for maintenance.

The following are changes in the release:

- enhanced the info for snapshot administration
- a few GUI adjustments
- fixed a bug in search logs, the search was not localized
- fixed a bug in delete logs and save logs to permanent store
- fixed a bug in removal of the --delete parameter
- some adjustments in search and sort (in logs and all profiles)
- some localization fixes Norwegian
- some localization fixes Chinese (Simplified)
- removed possibility for encrypted backups linked with RcloneOSX
- fixed a couple of memory leaks
- refactor of code and cleanup
- enhanced awareness if remote servers are not available

## Version 5.8.6

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.8.6) 16 May 2019.

The following are new features and updates in version 5.8.6.

- in snapshots save day and plan on each snapshot task
- cleanup of GUI snapshots and copy files
- fixed a bug i rsync parameters, now all default parameters might be deleted
- added possibility to execute a selected tasks Now in RsyncOSXsched app (menu app)
- added possibility to auto execute tasks in RsyncOSXsched app (menu app) when local disk is attached
- some refactor and cleanup of code
- [localization](/post/localization/)
	- RsyncOSX and RsyncOSXsched are prepared for localization
	- RsyncOSX is translated to Chinese (Simplified) and Norwegian (default language is English)
	- the Chinese (Simplified) translating by [StringKe](https://github.com/StringKe)
	- RsyncOSXsched is translated to Norwegian (default language is English)
	- volunteers for translating to other languages are wanted

## Version 5.8.1

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.8.1) 21 March 2019.

![](/images/RsyncOSX/master/nextversion/nextversion.png)

- quit RsyncOSX by red button upper left main window
- RsyncOSX center itself in screen when started
- view all profiles and configurations by menu button (moved from tab view)
- backup now and automatic backup my be executed from any view (tab) by menu buttons or shortcuts
- clean up of code and some bugfixes
- configuration is available by shortcut ⌘, (Preferences)

## Version 5.7.3

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.7.3) 16 February 2019.

The following are included in the release:

- fixed a [bug](https://github.com/rsyncOSX/RsyncOSX/issues/1061) in user selected parameters to rsync
- added function for [remove](https://github.com/rsyncOSX/RsyncOSX/issues/1059) the "-e ssh" flag, seems to be required if using RsyncOSX and ReadyNAS utilizing rsync daemon on server side



## Version 5.7.1

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.7.1) 6 February 2019.

There is fixed one bug causing RsyncOSX to crash if other versions than 2.6.9, 3.1.2 or 3.1.3 of rsync is used. This applies to both local rsync and remote rsync if remote servers is utilized.

The following fixes and enhancements will be part of next release:

- fixed bug if not supported versions of rsync is utilized
- added new plans for deleting snapshots, there is now two plans
	- last: keeps **last** selected day previous months, last selected day this mont and all snapshots this week
	- every: keeps **all** last selected day previous months, every selected day this mont and all snapshots this week
	- selected day in user configuration
- some other minor enhancements as well

This will be the last version compiled and released with current released version of Xcode and Swift. Xcode 10.2 and Swift 5 are out as beta and most likely will be released within some months.

## Version 5.6.2

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.6.2) 1 January 2019.

This is a maintenance release: cleanup in code, minor bugfixes and [plan](/post/plansnapshots/) for snapshots.

## Version 5.6.1

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.6.1) 6 December 2018

In this release executing scheduled tasks is **moved** to the [menu app](/post/menuapp/).

The following changes compared to version 5.5.7 are:
- a lot of cleanup in code (delete of dead code)
- delete code for execution of scheduled tasks, the [menu app](/post/menuapp/) executes scheduled tasks, add and delete schedules in RsyncOSX
- some enhancements in restore and restore defaults to temporary restore catalog if set in user config
- some enhancements in cleaning (deleting) snapshots and log records
- and as always some bugfixes

If both RsyncOSX and RsyncOSXsched (the menu app) is running, RsyncOSX is sending a reload message to the menu app every time there is a change to either a configuration or a schedule. The menu app keeps track of scheduled task in all profiles.

If you are not utilizing scheduled tasks don´t install the RsyncOSXsched app.

**Next release** will include **plans for snapshots**. A plan for snapshot is a template for which snapshots to keep and which to delete.

## Version 5.5.7

Released 22 November 2018.

The following are changes in the release:
- refactor batch tasks
- the userconfig is refactored
- and some minor bugfixes and tweaks (gui)
- the RsyncOSX.app is [notarized](/post/notarized/)
- in the All profiles tab info about used and available remote storage

Here are some screenshots of what is in this [version](/post/nextversion/).

## Version 5.5.5

Relased 22 Oct 2018.

The following are changes in the release:
- enhanced quick backups
- enhanced copy single files
- enhanced snapshots
- bugfixes

I am not able to predict and test for all possible user interactions. I have tried to smoke out most bugs and make the code as robust as possible. The most common errors are nil pointer errors and not taking care of it if a program variable is not initialized nor has a default value when accessed. I have also tried, by program logic, to verify required input ahead of an action. I believe the last version is robust. RsyncOSX can be minimized during operations and all tasks can be aborted at any time. But there are no guarantee that RsyncOSX will handle all situations.

If RsyncOSX does halt or crash during operation there is no damage to files or deletion of files in the source. The source is only read during synchronize and snapshot tasks. And always do a restore to a temporary restore catalog.

## Version 5.5.3

Released 29 September 2018.

- supports macOS Mojave and the new Dark Mode
- no logging, minimum or full logging enable/disable in user config
- bugfixes

## Version 5.5.0

Released 8 September 2018.

This is a maintenance release. The following changes are applied:

- bugfixes
- added buttons and tooltips for tasks i main menu (top row)
- changed some of the icons for menu buttons
- refactor in parts of code

## Version 5.4.1

Released 16 August 2018.

The primary goal for this release is adding [verify](/post/verify/) of backups. There are also some other and minor fixes as well.

- new function [verify](/post/verify/)
- if task is selected in Synchronize view, only logs for selected task is presented in log view
- fixed preserving sort direction and selection of logs
- in [snapshots](/post/snapshots/) enter number of snapshots to delete directly
- cleaned up in [copy single files](/post/copysinglefiles/) and fixed a memory leak
- a new info view showing output from rsync during execution of single tasks

## Version 5.3.9

Released 22 July 2018

- deleting or adding [temporary path restore](/post/userconfiguration/) catalog is not working properly
	- used in Copy Single files
	- and in new function for full restore
- first execution of a task is not logged properly
- various minor fixes in GUI here and there
- some minor refactor of code
- in automatic backup added percent completed each row
- added temporary catalog for restore
- added slider for deleting old snapshots
- collecting errors from rsync to view and correct
	- sometimes rsync throws error and halts execution of task, useful to check which errors is thrown
- added observers in **menu app** (RsyncOSXsched) and RsyncOSX notifying when Mac is going to sleep and awake

## Version 5.3.7

Released 18 June 2018.

A **bug** in automatic backups is fixed, the bug causes RsyncOSX to crash if reporting more than 1000 files to be transferred. The bug is due to wrong number formatting.

Creating the "restore part" of a task is removed, how to do a full restore is reimplemented. There are also some enhancements in the info part, caching of information, select and delete log records and a better check if menu app is installed.

- [full restore](/post/fullrestore/)
- [logging](/post/logging/)
- [caching of information](/post/caching/)
- compiled with latest version of Xcode, version 9.4.1 (9F2000)

## Version 5.3.5

Released 1 June 2018.

* some minor bugfixes
* some minor GUI tweaks
* some enhancements scheduled tasks
* some refactor of code
* size of app icon is fixed (reduced), thx to [Zsolt Sándor](https://github.com/graphis)
* compiled with latest version of Xcode, version 9.4 (9F1027a)

## Version 5.3.1

Released 23 April 2018.

Rsync does not support encrypted backups directly. There is another tool rclone which does. By utilizing RsyncOSX and [RcloneOSX](https://github.com/rsyncOSX/rcloneosx) to synchronize encrypted backup to **remote servers** running OS as FreeBSD, Linux, Solaris and so on. RsyncOSX executes the rclone and rsync command line tool in one go. The administration of the rclone part is done in [RcloneOSX](https://github.com/rsyncOSX/rcloneosx).

Please read the documents about [encrypted](/post/Encrypted) backups.

There is also a new feature [automatic](/post/Automatic) backups. RsyncOSX does a check if there are data to be transferred or deleted and for those configurations a backup is automatic executed.

## Version 5.2.1

Released 28 March 2018.

The RsyncOSXsched.app is not required to install, it is the [menu app](/post/Menuapp) for scheduled backups.

- new application icon by [Zsolt Sándor](https://github.com/graphis)
- fixed a bug in schedule
- some other enhancements, se below..

Within the dynamic info view a progress bar informs about the progress. There is a Select button to select all tasks with changed files compared to backup catalog.

## Version 5.1.1

Released 27 February 2018

- added a [menu app](/post/Menuapp)
to execute scheduled backups, the menu appis a minimal version of RsyncOSX only capable of executing scheduled tasks
	- all editing of tasks and schedules are within RsyncOSX
- added notifications when scheduled task is completed
- the scheduled part is redesigned, to activate a schedule select start date and time and type of schedule.
	- the schedules are active until *deleted* or *stopped*
	- schedule once only executes once, daily and weekly until stopped or deleted

## Version 5.0.0

- released 1 February 2018
- [snapshot](/post/Snapshots) is the main new feature in this release
- enhancements in Quick Backup
	-	selecting the i-button checks and estimates the number of changed files compared to the remote storage
	- select which tasks to be executed and press the play button for executing tasks immidialaty
	- the progress of each task is presented (require an estimate first - the i-button)
- some minor cleanup in the schedule part

## Changelog prior version 5.0.0

Changelog prior to version 5.0.0 is deleted. The initial release was 14 March 2016 and code is rewritten since the initial release.


## Version 0.5 beta

- initial listing 14 March 2016, released on MacUpdate as well
