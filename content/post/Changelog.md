---
layout: post
title:  "Changelog"
permalink: Changelog
---
I am using the application on a daily basis and it evolves during my own use. Suggestions for new *features*, *enhancements* and *bug reports* are more than welcome. [Please add an issue](https://github.com/rsyncOSX/RsyncOSX/issues) regarding requests or bugs. For more information about signing and notarizing of RsyncOSX see [the notarized info](/Notarized).

## RsyncOSX on macOS Catalina

If you are installing on macOS Catalina and utilize a local version of rsync, execute the `rsync` utility in a terminal window before using RsyncOSX. There is a process of granting access for the `rsync` utility before using it by RsyncOSX. MacOS Catalina will also ask permission for accessing your home catalog first time you start RsyncOSX.

If you also utilize the menu-app (RsyncOSXsched), be aware of you might have to force quit RsyncOSX the first time you start the menu-app. This is because the macOS Catalina ask for permissions when starting the menu-app for the first time and RsyncOSX is not closed automatically when starting the menu-app. This might happen only once first time start on the macOS Catalina.

### Some words about RsyncOSX

RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of `rsync` to synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from those remote servers.

The UI can for users who dont know `rsync`, be difficult or complex to understand. It is not required to know `rsync` but it will ease the use and understanding of RsyncOSX. But it is though, possible to use RsyncOSX by just adding a source and remote backup catalog using default parameters.

RsyncOSX supports synchronize and snapshots of files.

If your plan is to use RsyncOSX as your main tool for backup of files, please investigate and understand the limits of it. RsyncOSX is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## Version 6.2.5 release candidate

[Updated](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.2.0) 14 April 2020.

The release candidate will be ready for release in beginning of May 2020.

- batch is removed and replaced with multiple selection of tasks to execute
- Italian localization added
- clean up of GUIs and code
- refactor of the Restore part
- updated the GUI of menu app (for executing scheduled tasks)
- logging rsync errors to file (not yet in release candidate, but in code)

![](/images/RsyncOSX/master/nextversion/italian.png)
![](/images/RsyncOSX/master/nextversion/restore.png)
![](/images/RsyncOSX/master/nextversion/schedule.png)

## Version 6.2.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.2.0) 27 February 2020.

The release is **signed and notarized**.

- restore single files and the full restore are combined
- cleaned up some other views as well
- cleaned (refactor) up some code

## Version 6.1.7

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.1.7) 5 February 2020.

The release is **signed and notarized**.

There are a few minor changes and enhancements in this release. The most noticeable change is the possibility to select another profile direct from the main, schedule and snapshot view (not from the profile dropdown menu). There are also some other minor changes which improves the usability of RsyncOSX. localization are updated as well.

## Version 6.1.5

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.1.5) 11 January 2020.

The release is **signed and notarized**.

- added German and French localization
- fixed a minor bug
- added input control in add configurations
- some GUI changes due to new localization

## Version 6.1.0

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.1.0) 24 December 2019.

The release is **signed and notarized**.

- added new type of task `syncremote`
- added possibility to remove the trailing `/` when adding tasks, if you remove the trailing `/` be sure you understand what it means
- added parameter to set `$date` on backup folder
- refactor of schedule
- check of schedule logs
- minimized GUI of the menu app

If you have any suggestions for enhancements or if you discover bugs, [please report an issue](https://github.com/rsyncOSX/RsyncOSX/issues).

## Version 6.0.1

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.0.1) 10 November 2019.

The release is **signed and notarized**. The major changes are:

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

**Important** - from macOS 10.15 Catalina, [notarization is required](/Notarized) by default for all software.

The major part (about 80%) in this version are refactor and cleanup in code. Refactor is mainly for decoupling of code and make RsyncOSX easier for maintenance.

The following are changes in the release:

- enhanced the info for snapshot administration
- a few GUI adjustments
- fixed a bug in search logs, the search was not localized
- fixed a bug in delete logs and save logs to permanent store
- fixed a bug in removal of `--delete` parameter
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
- added possibility to execute a selected tasks `Now` in RsyncOSXsched app (menu app)
- added possibility to auto execute tasks in RsyncOSXsched app (menu app) when local disk is attached
- some refactor and cleanup of code
- [localization](/Localization)
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
- configuration is available by shortcut `⌘,` (Preferences)

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

This is a maintenance release: cleanup in code, minor bugfixes and [plan](/Plansnapshots) for snapshots.

## Version 5.6.1

[Released](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v5.6.1) 6 December 2018

In this release executing scheduled tasks is **moved** to the [menu app](/Menuapp).

The following changes compared to version 5.5.7 are:
- a lot of cleanup in code (delete of dead code)
- delete code for execution of scheduled tasks, the [menu app](/Menuapp) executes scheduled tasks, add and delete schedules in RsyncOSX
- some enhancements in `restore` and restore defaults to temporary restore catalog if set in user config
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
- the RsyncOSX.app is [notarized](/Notarized)
- in the All profiles tab info about used and available remote storage

Here are some screenshots of what is in this [version](/nextversion).

## Version 5.5.5

Relased 22 Oct 2018.

The following are changes in the release:
- enhanced quick backups
- enhanced copy single files
- enhanced snapshots
- bugfixes

I am not able to predict and test for all possible user interactions. I have tried to smoke out most bugs and make the code as robust as possible. The most common errors are nil pointer errors and not taking care of it if a program variable is not initialized nor has a default value when accessed. I have also tried, by program logic, to verify required input ahead of an action. I believe the last version is robust. RsyncOSX can be minimized during operations and all tasks can be aborted at any time. But there are no guarantee that RsyncOSX will handle all situations.

If RsyncOSX does halt or crash during operation there is no damage to files or deletion of files in the `source`. The `source` is only read during `synchronize` and `snapshot` tasks. And always do a restore to a temporary restore catalog.

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

The primary goal for this release is adding [verify](/Verify) of backups. There are also some other and minor fixes as well.

- new function [verify](/Verify)
- if task is selected in Synchronize view, only logs for selected task is presented in log view
- fixed preserving sort direction and selection of logs
- in [snapshots](/Snapshots) enter number of snapshots to delete directly
- cleaned up in [copy single files](/CopySingleFiles) and fixed a memory leak
- a new info view showing output from rsync during execution of single tasks

## Version 5.3.9

Released 22 July 2018

- deleting or adding [temporary path restore](/UserConfiguration) catalog is not working properly
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

- [full restore](/Fullrestore)
- [logging](/Logging)
- [caching of information](/Caching)
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

Rsync does not support encrypted backups directly. There is another tool `rclone` which does. By utilizing RsyncOSX and [RcloneOSX](https://github.com/rsyncOSX/rcloneosx) to synchronize encrypted backup to **remote servers** running OS as FreeBSD, Linux, Solaris and so on. RsyncOSX executes the `rclone` and `rsync` command line tool in one go. The administration of the rclone part is done in [RcloneOSX](https://github.com/rsyncOSX/rcloneosx).

Please read the documents about [encrypted](/Encrypted) backups.

There is also a new feature [automatic](/Automatic) backups. RsyncOSX does a check if there are data to be transferred or deleted and for those configurations a backup is automatic executed.

## Version 5.2.1

Released 28 March 2018.

The RsyncOSXsched.app is not required to install, it is the [menu app](/Menuapp) for scheduled backups.

- new application icon by [Zsolt Sándor](https://github.com/graphis)
- fixed a bug in schedule
- some other enhancements, se below..

Within the dynamic info view a progress bar informs about the progress. There is a `Select` button to select all tasks with changed files compared to backup catalog.

## Version 5.1.1

Released 27 February 2018

- added a [menu app](/Menuapp)
to execute scheduled backups, the `menu app`is a minimal version of RsyncOSX only capable of executing scheduled tasks
	- all editing of tasks and schedules are within RsyncOSX
- added notifications when scheduled task is completed
- the scheduled part is redesigned, to activate a schedule select start date and time and type of schedule.
	- the schedules are active until *deleted* or *stopped*
	- schedule `once` only executes once, `daily` and `weekly` until stopped or deleted

## Version 5.0.0

- released 1 February 2018
- [snapshot](/Snapshots) is the main new feature in this release
- enhancements in Quick Backup
	-	selecting the i-button checks and estimates the number of changed files compared to the remote storage
	- select which tasks to be executed and press the play button for executing tasks immidialaty
	- the progress of each task is presented (require an estimate first - the i-button)
- some minor cleanup in the schedule part

## Version 4.9.6

- released 9 January 2018
- a couple of minor bugfixes
	- in logging
	- in the ssh-tab for assisting setup of password less logins, when port number in use there is a bug, thx to [pierre-fromager](https://github.com/pierre-fromager) reporting the bug
	- bug in copy files when ssh port in use
- new function for **quick backups**, sort and select which tasks to be executed in one go
- new function for **info about backup locations**
- new function for doing **quick backups** from the **info about backup locations**
- in parameter view the rsync parameter `--compress` can be toggled on/off
- sort and filter in **quick backups** and **info about backup locations**

## Version 4.9.2

- v4.9.2 released 17 Dec 2017
- focus on GUI single tasks and batch
- adding several shortcuts
	- after selecting a row the following shortcuts are effective
	- `⌘E` - shortcut for edit task
	- `⌘O` - shortcut for rsync parameters to task
	- `⌘D` - shortcut for delete task
	- `⌘R` - shortcut for immediate execute task
	- `⌘A` - Abort task

## Version 4.9.1

- released 1 Dec 2017
- fixed a bug in batchview causing batch not executing properly

## Version 4.9.0

- released 28 Nov 2017
- new buttons are implemented
- fixed a typo and some minor fixes

## Version 4.8.6

- released 23 Nov 2017
- logging result after execution of tasks is fixed
- added possibility of logging, either minimum or full, output from rsync to loggfile in `Documents/rsynclog.txt`
	- the logging to file is default off when starting RsyncOSX, status of logging is not saved in userconfiguration
	- the log function appends new logs, be careful not logging all actions
- fixed some other minor glitches
- added number of days since last backup in Synchronize view

## Version 4.8.2

* released 15 Nov 2017
* it is minor maintenance release, a couple of bugfixes and enhancements in batchview

## Version 4.8.1

* released 7 Nov 2017
* this will be the last release for RsyncOSX for some time

The main focus in the version 4.8.1 is UX-design (user experience). The objective is to make the UX-experience in RsyncOSX as good as possible.
## Version 4.8.0

* released 25 Oct 2017
* redesigned the schedules part
* fixed a major bug in batch mode
	- hiding view in batch mode previous versions of RsyncOSX will reset the batch task
	- there are no risk for damaging files, just restart batch task and rsync(OSX) continues from where it stopped
* some other bug fixes as well
* the .dmg file is built on a mounted NOT APFS (SMB mount) filesystem to avoid problems mounting the .dmg file on non APFS systems


## Version 4.7.5

* released 12 Oct 2017
* fixed bug in batch function

## Version 4.7.0

*Caution : there is a bug in the batch function, working on a new release.*

In version 4.5.1, configurations and schedules are kept in memory utilizing singeltons. In version 4.7.0 singeltons are replaced by dynamic objects. This results in cleaner code, less couplings and less housekeeping. Stateful objects are difficult and increases complexity in the code.

* released 10 Oct 2017
* major refactor of several parts (eliminating singeltons)
* changed how to get list of remote files (in Copy Files)
* changed how output from rsync executes and information from rsync output is collected
	- all the analysis on the output is done after a process termination is observed
	- in batch mode calling next task after a 1.0 second stop, if not a process termination might be observed before output from task is completed
* fixed a bug in batchview if rsync discover an error, now rsync aborts and close batchview and notifies about the rsync error
* fixed a bug in setting user selected parameters to rsync (the two first parameters)
* and fixed other minor bugs as well

## Version 4.5.1

Built with Xcode 9 GM.

There is a rsync-3.1.2.dmg included which is a built version of latest rsync. To install this version of rsync please make a catalog in your home directory (or use /usr/local/bin) and make RsyncOSX aware of using the new rsync in [userconfig](/UserConfiguration).

* released 13 Sept 2017
* using [SwiftLint](https://github.com/realm/SwiftLint) has caused several and major rewrites in parts of code
	* some of the classes are yet not adapted to SwiftLint rules
* code is adapted to Swift 4
* fixed a bug when choosing task for batch, an `execute` of task might accidentally start when select or deselect batch task
* fixed a bug in discover new version of RsyncOSX
* there are numerous internal changes and quite a few minor bugfixes
* refactor filter (search) functions in logs and copy files
* fixed a bug causing RsyncOSX to crash if loading new profile during a test for TCP connections
* added parameter `--max-delete=-1` to secure no execution of task if files will be deleted during run (user selected in setting rsync parameters)

## Version 4.4.6

* released 3 July 2017
* rewrite of code for executing single and batch tasks, reduces the complexity and size of code and it separates the view and model
* fixed a bug in Schedules some other minor bugs
* removed test for TCP connections remote servers to a button in Synchronize view (no automatic check for connections)


## Version 4.4.0

* released 8 June 2017
	* compiled with latest release 8.3.3 of Xcode (which was released June 2017)
* Seems like the [logging](/Logging) problem is partly solved in 30 May 2017 update
* Added Abort when real task is executing
* Refactor of Copy Single files/directory
	* in userconfig set temporary restore catalog (for single files or directory)
	* display size remote files
	* double click on row to get remote filelist
	* double click on row to restore files or directory to temporary (local) catalog
* Clean up of other parts of code

## Version 4.3.0

* released 8 May 2017
* assist in setup of [passwordless logins](/PasswordlessLogin)
	* see [doc](/ssh) - documentation in progress
* couple of bugfixes

## Version 4.2.5

**Bug** in version 4.2.5 causes RsyncOSX to crash if RsyncOSX is minimized during execution of a task. Bug is fixed and will be released in version 4.3.0.

**Next** release (version 4.3.0) will probably include some functionality for assisting setup of [passwordless logins](/PasswordlessLogin). Don't know when it will be released. Summer is coming and further development of RsyncOSX will be slowed down during summer. I am currently working on this release now and (slowly) progressing...

* released 23 Apr 2017
* minor bugfixes and cleanup of code
* compiled with new release of Xcode (version 8.3.2)
* adjusted the parameters to rsync
* adjusted the schedule

In the parameter to rsync, if `backup` option is selected RsyncOSX adds the directory to the backup catalog (for saving changed and deleted files). Choose either suffix for FreeBSD or Linux. Neither of them works on **local backup** macOS (have to test more). But, if you copy and paste the FreeBSD suffix in a terminal window it works on macOS (it adds the correct timestamp to the changed files in the backup directory).

The schedule now informs if a scheduled backup plan is to short ahead. A weekly backup must be at least seven days ahead of current date and time.

## Version 4.2.0

* released 10 April 2017
* compiled with new release of Xcode (version 8.3.1)
* enhanced the batchwork part
* fixed a couple of minor bugs
* some cleanup in code
* reorganized Help
* there is an issue when RsyncOSX counts files to be transferred in *batchmode*, the issue does not introduce any faults (informal only)
* there is also an issue when RsyncOSX is logging, sometimes RsyncOSX does log 0 files and not the actual number of files and size of transfer (informal only)

## Version 4.1.0

* released 19 March 2017
* fixed one bug in parameters to rsync (causing RsyncOSX to crash)
* new help function - opens relevant html page in browser
* added new info using rsync version 3.1.2 (number of *new* and *delete* files)
	* see user configuration how set other version of rsync

## Version 4.0.0

* released 8 March 2017
* new application icon by Forrest Walter (this is the primary reason why releasing a new version)
* added new functionality in `Copy files` - double click on source get list of files from remote server

## Version 3.9.7

Sometimes rsync throws errors and does not execute as expected. Single task is implemented as queue of work (`estimate`, `execute` and `done`). If `estimate` or `execute` fails (by some reason) the user has to be made aware of situation and fix it.

RsyncOSX checks output from rsync for string *rsync error:*. If found Synchronize view is notified, error is marked (in red) and work queue is reset if option in userconfig (see below) is set. To test enter a not valid user name for a remote server ([edit task](/SingleTask) in Synchronize view).

Other changes:

- released 2 March 2017
- some refactor and several cleanup of code
- Added reporting any file errors (in profile) to Synchronize view.
- There is also fixed a minor bug in Profiles.
- In About menu reference to GitHub Pages about Changelog and Documentation of RsyncOSX

## Version 3.9.5

Version 3.9.5 might **crash** for some user. This is due to localized string representation of dates in logs. RsyncOSX only accepts `en_US` format of dates in logs. Comparing and sorting other localized string representation of dates causes a crash.

If RsyncOSX crash during startup please delete the schedule and loggfile: `Documents/Rsync/MacID/scheduleRsync.plist` (deleting this file only deletes any schedule and logs).


- released 28 January 2017
- I´m not adding any major new functionality to RsyncOSX, only minor enhancements.
- the focus in this release candidate is to make logs more informal and stable
- logs are now sorted with most recent log on top (first row in table)
- active schedules are marked red
	- number of logs in each schedule
	- manual execution of tasks are logged under start date `1 Jan 1900 00:00`
- dates are forced to "en_US" localization to prevent RsyncOSX from crashing if the preferred language of macOS is other than english (e.g. Norwegian)

## Version 3.9.1
- released 19 January 2017
- added a few tweaks regarding radio buttons in Synchronize view and deselect row after delete actions
- moved Add button new configurations into tab view and added some more checks when adding new configurations
- In Sch

## Version 3.8.6
After releasing this version I will not release new versions for some time. I have to focus on my new job (start 2 January 2017) for some time. I will continue to develop RsyncOSX in the future, but the number of new releases will drop compared to 2016.

- fixed bug in profiles
- added an alternative suffix (in parameters to rsync)
- added delete log rows in log view
- even more cleanup of code

## Version 3.7.7
- released **23 December 2016**
- fixing one bug in Profiles introduced another bug causing logs to be overwritten

## Version 3.7.6
- released **23 December 2016**
- fixed yet another bug in Profiles
	- bug causing old configurations and schedule data not properly cleaned when new profile is created
- compiled with latest version 8.2.1 of Xcode
- the are several parts of code which is refactored
	- cleaned up external references (in About and NewVersion)
	- added guard statements to make code safer
	- fixed a bug in Main.storyboard referring to a non existing class
	- refactor of computing parameters to rsync

## Version 3.7.2
- fixed a bug in set optional path for rsync

## Version 3.7.1
- updated **13 December 2016**, compiled with new version 8.2 of Xcode released 12 December 2016
- released **10 December 2016**
- fixed a bug `--suffix` parameter used together with `--backup` parameter to set date and time suffix (e.g `changed-file_2016-12-10.15.25`) of changed or deleted files in backup directory
- split `--backup` parameter and `--suffix` in parameter view
- refactor of code for rsync parameters and logging
- speed of sorting and filter logs improved
- added display both `--dry-run` and `real run` of rsync command in Synchronize view

## Version 3.6.5

- released **23 November 2016**
	- this will be the last release for some time (most likely last release this year)
	- there are no known issues or request for new features
	- I will continue develop RsyncOSX in 2017, there are some internal parts which should be refactored
- new About view (links to docs, changelog and check for new versions)
- fixed a bug in Edit configurations (reset values when new configuration is loaded)
- some minor cleanup of code

## Version 3.6.1

- released 15 November 2016
- logs part is changed, text search for **remote server**, **local catalog** or **executed date/time**
- there is a bug in deleting ssh-port - **fixed**
- there is a bug in enabling Profiles menu when RsyncOSX is started on a Mac for the first time (Profiles menu is not enabled) - **fixed**
- sometimes output from rsync is set to **nil** (in RsyncOSX), doing an unwrap of nil value causes RsyncOSX to crash - **fixed**


## Version 3.5.5

- new image updated **10 November 2016** : some minor GUI tweaks and automatic dismiss after 10 seconds in some of the views
- new image updated **5 November 2016** : if selecting new profile before background check for connection is completed RsyncOSX might crash, fix is done and new image is uploaded. Background check is executed when Synchronize view loads and remote servers not responding is marked red.
- released 3 November 2016
- fixed a couple of bugs in automatic dismiss of popup views (when scheduled backups are running and in Synchronize view a popup informs of backup)
- some minor refactor of code


## Version 3.5.1

- new image updated **2 November 2016** : added check for optional version and path of rsync
- new image updated **1 November 2016** : "moved" GUI updates in background (Scheduled operations) to main thread - making RsyncOSX unstable if not - throwing "CoreAnimation: warning, deleted thread with uncommitted CATransaction" if not
- **caution** : a bug in Scheduled jobs caused version 3.5.1 released 30 October 2016 to crash - a new image of version 3.5.1 uploaded late 30 October 2016.
- released 30 October 2016
- fixed a bug in version 3.5.0 deleting/stopping schedules causing a nil pointer exception and crash
  - bug was "introduced" when compiling RsyncOSX with latest release version 8.1 of Xcode
- notify new versions of RsyncOSX by delegate
- mainly a maintenance release, some bigger internal changes and some GUI tweaks
- RsyncOSX is more stable than ever
  - replaced states by work queue (using states get complex even with a few states)
  - I am learning Swift every day and [refactor code](https://en.wikipedia.org/wiki/Code_refactoring) is important
- code ([master](https://github.com/rsyncOSX/Version3.x/tree/master)) at Github is updated with last commits
- added double click for executing single task and select profile
  - double click first time executes a dry run, another double click after dryrun executes the real task
  - enable/disable double click in user configuration


## Version 3.4.1

- released 20 October 2016
- copy and paste was by mistake not in 3.4.0 - now it is...
- there was an issue with Copy files (search and copy single files or catalogs) - if you experience any problems with copy files in version 3.4.1 please update to last image of version 3.4.1


## Version 3.4.0

- released 19 October 2016
- added profiles - select profiles from the File menu, profiles is just new catalogs for storing configurations and schedules files.
- backup of single files in Add view, only backup part is added for single files, use Copy Files to search and restore single files
- some minor internal cleanup and fixes, adjusted Copy Files view
- added abort in Copy Files (terminates search process)
- in logs view selecting row selects logs for selected remote server
- removed test mode in RsyncOSX - replaced by profiles
- user configuration available from Main tab, Add tab and Schedule tab
- in main tab when rsync is changed in user configuration, if row is selected rsync command in view is updated
- counting of files and directories from rsync output is more robust, only version 3.x of rsync counting directories remote


## Version 3.3.0

- released 6 October 2016
- capture of more precise info about files, tested on both stock version on rsync and 3.1.2 of rsync (only version 3.x counts directories)
- fixed a bug not saving path for other version of rsync
- added backup in rsync parameters
  - changed files are moved to backup location (default ../backup) and appended a timestamp before updated files are transferred from source to destination
  - useful when saving versions of e.g. documents
- fixed a memory leak in scheduling of tasks
  - after the last release 4 Oct 2016 it seems that there are no memory leaks (at least the graphic memory debugger in Xcode reports no leaks as well as the Xcode instrument Memory Leaks)


## Version 3.1.5

- released 24 Sept 2016
  - image is updated 26 Sept 2016 (fixed a few minor glitches)
- added detailed logging
  - logging switch on/off in Configuration
- hopefully no more releases for some time after this release


## Version 3.1.0

- updated 22 Sept (released 20 Sept 2016)
- scheduling of tasks
- added (22 Sept 2016) adding local volumes by graphical window or drag and drop from Finder
- a few minor bug fixes (22 Sept 2016)


## Version 3.0.5

- updated 15 Sept 2016
- copy of single files or catalogs from remote storage
  - doing a restore require to press the Estimate button twice, once for a -- dry-run (estimate) and the the real run (execute)
- some visual enhancements
- Scheduling of tasks is **not yet** included in this version (will be in version 3.1.0)
  - tasks might be scheduled in version 3.0.5 but not executed


## Version 3.0.0

- built on macOS 10.12 GM by Xcode 8 GM (GM = "gold master")
- supports macOS 10.11 and macOS 10.12

What is **NOT** implemented in version 3.0

- no execution of Scheduled task, but scheduled task may be added, stopped and deleted
  - the code for execution of scheduled tas has to be revised and tested
  - will come in version 3.1.0
- no copy of single files or catalogs from remote servers
  - will come in version 3.1.0
- no detailed logging
  - will come in version 3.1.0

## Changelog prior version 3.0.0

Changelog prior to version 3.0.0 is deleted. The initial release was 14 March 2016 and code is rewritten since the initial release.


## Version 0.5 beta

- initial listing 14 March 2016, released on MacUpdate as well
