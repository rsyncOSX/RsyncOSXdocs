+++
author = "Thomas Evensen"
title = "Changelog"
date = "2022-05-07"
description = "Changelog"
tags = ["changelog"]
categories = ["general information"]
lastmod = "2022-05-04"
+++
RsyncOSX is [signed and notarized](/post/notarized/). Please see info about [the latest version of rsync in install](/post/rsync/).

## Minor non critical issue 

7 May 2023

If you in the main view select a task and then to the logs view, RsyncOSX filter the logs for only the selected task. If you then return to main view, select a new profile, the index to the previous selected task in previous profile is not cleared. This might cause the logs view to present only a few or none logs for the new profile. Workaround: select a task and deselect it. Issue is fixed in code.

{{< image src="/images/Temporary/main.png" alt="" position="center" style="border-radius: 8px;" >}}
{{< image src="/images/Temporary/logs.png" alt="" position="center" style="border-radius: 8px;" >}}

## Version 6.8.0 build (22) 

Released 13  April 2023

This version was released as release candidate in March. It is stable and status is changed to latest release.

- the schedules part is removed from build
- some minor cleanup in code

There was one critical issue with **the schedule part** of RsyncOSX. On macOS Ventura 13.3  the scheduled part did not work. The issue was that the schedule part did not execute the external process which executes the real synchronize task.  I have therefore decidede to remove the schedule function in RsyncOSX. Over the time only a few users have used it. Most important for me is to enable a stable RsyncOSX and the scheduled part was either due for a serious update or remove it. For me the answer was **remove it**.  

## Version 6.7.6 build (21) 

Released 13 January 2023 

Compiled on Apple Silicon (M1 Pro) by Xcode 14.2 as a Universal macOS Binary on macOS Ventura. 

I have also commenced writing [an article](/post/built/) about how the apps (RsyncOSX and RsyncUI) are built. It is work in progress and documents some of the main building blocks for the apps.

This release is **not changed** since the release candidate. There is **no need** to update if already dowloaded the release candidate from 23 December 2022.

- the check for new versions of RsyncOSX  is changed (internal stuff)
- all new tasks are marked with red text in date field until a real synchronize is executed, a double click for estimate (dryrun) on a newly added task will change the text "not verified (dryrun)" to todays date in red, when the real run is executed the timestamp is written to the task
- there are also some other minor fixes and updates 

If the user decide to skip the dryrun and not verify the result, the user might delete and loose data if parameters to rsync is wrong according to what is expected. Like mixing up source and destination folders will most likely cause data to be deleted.

## Version 6.7.5 build (19) 

Released 18 November 2022

Compiled on Apple Silicon (M1 Pro) by Xcode 14.1 as a Universal macOS Binary.

**The release candidate from 10 November is stable and becomes the new release**, existing users of the release candidate do not need to update.

The major work within this version is rewrite of code to utilize Swifts `async` and `await` for asynchronous execution of tasks. Utilizing `async` and `await` makes the code simpler and cleaner. The need for callback functions are reduced.  And lesser code is better code. Asynchronous execution is a key part of RsyncOSX. The completion of a task is not known ahead and whenever a task is completed next action is executed. Next action is e.g. execute next synchronization task, present output from rsync or present a list of files. 

There are also a few fixes within the snapshot part of RsyncOSX, some cleanup and deletion of unused code. 

There are no changes to the GUI part, only internal changes.

## Version 6.7.4 build (18)

Released 8 September 2022

Compiled on Apple Silicon (M1 Pro) by Xcode 14.0 as a Universal macOS Binary.

Built on macOS Ventura by Xcode 14.0. There are fixed a couple of minor glitches. All glitches are related to a few missing updates in a couple of views.

## Version 6.7.3 build (17)

Released 4 May 2022

Compiled on Apple Silicon (M1 Pro) by Xcode 13.3 as a Universal macOS Binary. Users who already have updated to this version does not need to reinstall it.

The button for "Add task" is moved to the sidepanel. The sidepanel buttons are slightly reorganized. There are a few localization fixes in German and Norwegian. And there are also some views which are adjusted as well.

This is a minor maintenance release.

## Version 6.7.2 build (16)

Released 13 April 2022

Compiled on Apple Silicon (M1 Pro) by Xcode 13.3 as a Universal macOS Binary.

This is a minor maintenance release. The [Add part](https://rsyncosx.netlify.app/post/addconfigurations/) is moved to the top menu of RsyncOSX. There is also some minor cleanup in the localizations.

The [issue](https://github.com/rsyncOSX/RsyncOSX/issues/2062) is fixed.

## Version 6.7.1 build (15)

Released 21 February 2022

Compiled on Apple Silicon (M1 Pro) by Xcode 13.2.1 as a Universal macOS Binary.

The changes also includes the bugfix from version 6.7.0.

- **the userconfig** is now saved as JSON file, automatically transferred from the previous PLIST config file
  - userconfig are values like which version of rsync is utilized, restore path and so on
- accessing **the schedule part is moved to a button within main view**, the main percentage of the users of RsyncOSX does not utilize the schedule part and the change clean up the main tab view
  - the schedule part is by default hidden, enable the schedule part in the userconfig
- continue the cleaning of code and removing of not used code
  - the development of RsyncOSX commenced more than five years ago and there are still not used code which should be removed

## Version 6.7.0 build (14) - prerelease

Released 22 January 2022

Compiled on Apple Silicon (M1 Pro) by Xcode 13.2.1 as a Universal macOS Binary.

There is a bug when setting another path for rsync. The issue was easy to [fix](https://github.com/rsyncOSX/RsyncOSX/issues/2057) when found, it seems to be a minor bug in Xcode. A new build is uploaded as part of [current version](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.6.9).

There is **no need** to update if you are utilizing either default version of rsync in macOS or rsync installed by Homebrev.

Thx to [j-urich](https://github.com/j-urich) for reporting.

## Version 6.6.9 build (13)

Released 28 December 2021

Compiled on Apple Silicon (M1 Pro) by Xcode 13.2.1 as a Universal macOS Binary. There seems to be a **minor** bug in the About notifying about new version, the download button is not enabled. The latest release is [here](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.6.9).

The following are changed within this version:

- the restore part is refactored and more easy to use, for full restore select `./.` from the file list, estimate and then restore
- resize of the app now works OK for all views, all tables in all views are now resized when the app is resized
- and a few other minor GUI fixes as well

## Version 6.6.8 build (11)

Released 17 November 2021

Compiled on Apple Silicon (M1 Pro) by Xcode 13.1 as a Universal macOS Binary.

There are a few fixes within this release, the biggest change is internal.

- in Add view added GUI panel in selecting catalogs to synchronize
- this version discover if you are on a Apple Silicon and enables the correct path for Homebrew if version 3 of rsync is ticked on
- executing the schedule app, the menu app, is now from the File menu or by shortcut

The major work is internal. There might be several hundred or thousands of log records. Reading and loading log records into memory is moved to when they are needed. And not when the app is started or a new profile is selected. The change will improve memory footprint and speed up the application.

## Version 6.6.7

Released 22 September 2021

There are a couple of UI-fixes within this release. The release is also build by the Xcode 13 which was released yesterday.

## Version 6.6.5

Released 18 September 2021

There is a bug for new users of RsyncOSX. The bug was related to creating log records after executing a task and also caused some unwanted sideeffects.

## Version 6.6.4 - issue sync remote task - fixed

Released 11 September 2021

There is an issue with adding `syncremote` tasks in version 6.6.3. A syncremote task is pulling data from a remote server to local Mac.

The issue was caused only by a missing connection between a `@IBOutlet` variable and a `@IBAction` function. This is one of the drawbacks with storyboards. The connection must be established and somewhere during the cleanup of the UI the connection was dropped. And nothing was informing me about it was missing.

## Version 6.6.3

This build is for **macOS Big Sur and later**.

Released 25 July 2021.

This is a maintenance release with **one** bugfix and a **few** cleanups within the UI. The add view is cleaned up a little bit, profile info is moved to the sidebar.

## Version 6.6.2

This build is for **macOS Big Sur and later**.

Released 24 June 2021.

- fixed a bug in adding new configurations on a new install of RsyncOSX or creating a new profile

## Version 6.6.1

This build is for **macOS Big Sur and later**.

Released 21 June 2021.

This is primarly a maintenance release, some cleanup in code and fixing one "bug" when adding configurations. Default now when adding a configuration is adding trailing `/`. This was by mistake not in the 6.6.0 release. Adding a trailing `/` to rsync or not makes two very different tasks.

## Version 6.6.0

This build is for **macOS Big Sur and later**.

Released 6 June 2021

- the major work in this release is utilizing [Combine](/post/combine/)
- this release does only support macOS Big Sur and later versions of macOS (due to some features in Combine)

This release will be maintained in the future together with RsyncUI. Version 6.5.8 will still be available, but not maintaned. Integrating Combine into code and only supporting JSON does cleanup the code base for RsyncOSX. Less code is better code.

## Version 6.5.8

Released 24 March 2021

- there is fixed a bug in parameters to rsync, `-e ssh` is missing if there is **not** set an explicit ssh keypath and identityfile
- the above is only valid for remote servers, the parameter `-e ssh` causes the transferred data to be encrypted through a ssh tunell

## Version 6.5.7

Released 19 March 2021

- there are fixed a few layout (UI) issues in this release

## Version 6.5.6

Released 18 January 2021

There is a annoying bug in creating snapshots in version 6.5.4. It is one of the issues related to develop Swift and Storyboard applications. A button was removed in the Storyboard but not in code. And that one line of code causes a nil pointer exception and a crash.

- fixed a bug in creating new snapshot tasks
- some cleanup in Assist (in Add tasks) and some other parts

I am focusing on developing a SwiftUI based version of RsyncOSX and version 6.5.6 will probably be the last release for some time. Reported issues will be fixed (if bugs). There will most likely not be any further enhancements before the SwiftUI based version is released sometime in 2021.

## Version 6.5.4

Released 31 December 2020

The following is changed:

- there is a bug in deleting `snapshots`, please update if utilizing snapshots
- deleting snapshots is part of [administrating snapshots](/post/snapshots/)

## Version 6.5.3

Released 24 December 2020

The following are changes:

- application icon updated for Big Sur, by [Zsolt Sándor](https://github.com/graphis)
- Chinese (Simplified) localization updated, by [StringKe (Chen)](https://github.com/StringKe)
- a few minor bugfixes
- and several internal changes

In 2021 the main focus will be to develop a SwiftUI based version of RsyncOSX. And fix bugs when found. The internal updates in code is for the moment completed and any further updates will be as part of developing the SwiftUI based version.

I have no idea when a SwiftUI version wil be ready. I have a lot to learn about SwiftUI.

## Version 6.5.2

Released 4 December 2020

There are several internal changes in this version (refactor of code) to make the maintenance of the code more easy.

- there are a few changes to the main view, the main view is cleaned up and there is a new menubar on left side with the main actions for each view
- there are two new actions in main view, select a task and slide to left to execute, slide to right for delete
- the restore function is changed as well, there is now only possible to do restore, either full or file by file, to a temporary restore path
- there are fixed some minor bugs in the abort functions
- the bug in snapshot is fixed
- and there is some language updates as well

## Version 6.5.0

Released 12 November 2020

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

Released 23 September 2020

The following are changes in the release:

- default path for RsyncOSX config files is changed to `$HOME/.rsyncosx/macserialnumber`
  - existing users can choose to migrate or keep config files in previous default path which is `$HOME/Documents/Rsync/macserialnumber`
  - in About the used path for config files is presented
- the Restore part is adjusted
- and a few minor fixes
- due to the above issue, RsyncOSX version 6.4.6 and later is for macOS 10.15 and later

The reason for changing path for config file is there might be some issues for users utilizing primary store for `$HOME/Documents` catalog in iCloud. Storing config files at new path is more reliable. RsyncOSX can move config files for you. In File menu choose `Move config` and follow the instructions. The old config files are saved within the Documents catalog.

## Version 6.4.2

Released 22 August 2020

- fixed some bugs in logs and schedule part
- fixed issue when creating a snapshot task
- adding a snapshot task with remote server require to be online with server, the validate function check if online or not
- a lot of internal fixes and cleanup of old code
- the Add view is cleaned

## Version 6.4.0

Released 26 July 2020

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

Released 30 June 2020

- some localization updates (German, Chinese Simplified, French)
- added user set SSH keypath and identityfile, global and local settings
- refactor of RsyncOSX support SSH keypair creation
- enabled monitoring if drop in network connection during execution of tasks (only valid in macOS 10.14 and higher)

## Version 6.3.0

Released 26 May 2020

- added counting numbers in quick backup
- updatet a more precise counting when rsync is transferring files
- added clean logfile in view output from rsync
- some minor fixes and cleanups

## Version 6.2.6

Released 23 April 2020.

- batch is removed and replaced with multiple selection of tasks to execute
- Italian localization added
- clean up of GUIs and code
- refactor of the Restore part
- updated the GUI of menu app (for executing scheduled tasks)
- logging rsync errors to file
- added set ssh identity file (normally either id_dsa or id_rsa)
- added copy output from rsync to macOS clipboard

## Version 6.2.0

Released 27 February 2020.

- restore single files and the full restore are combined
- cleaned up some other views as well
- cleaned (refactor) up some code

## Version 6.1.7

Released 5 February 2020.

There are a few minor changes and enhancements in this release. The most noticeable change is the possibility to select another profile direct from the main, schedule and snapshot view (not from the profile dropdown menu). There are also some other minor changes which improves the usability of RsyncOSX. localization are updated as well.

## Version 6.1.5

Released 11 January 2020.

- added German and French localization
- fixed a minor bug
- added input control in add configurations
- some GUI changes due to new localization

## Version 6.1.0 - initial release

Version 6.1.0 was released 24 December 2019. The initial release was **14 March 2016**.
