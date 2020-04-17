---
layout: post
title:  "RsyncGUI Changelog"
permalink: RsyncGUIChangelog
---
![](/images/RsyncOSX/appstore/appstore.svg)
RsyncGUI is a sandboxed macOS app compiled with support for **macOS El Capitan version 10.11 - macOS Mojave version 10.15**. The application is implemented in Swift 5 by using Xcode 11.

Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing RsyncGUI (and rsync) at any time and still have access to all synchronized files.

The [App Sandboxing technology](https://developer.apple.com/app-sandboxing/) is a technology for protecting the user for malicious software. To release a macOS app on Apple Mac App Store require the app to execute inside a sandbox. RsyncGUI is an adapted version of [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX) to execute inside a sandbox. There are a few limitations compared to RsyncOSX.

## Some words about RsyncGUI

RsyncGUI is not developed to be an easy synchronize and backup tool. The main purpose is to ease the use of `rsync` and synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from remote servers. The UI might also be difficult to understand or complex if you don't know what `rsync` is. It is not required to know `rsync` but it will ease the use and understanding of RsyncGUI. But it is though, possible to use RsyncGUI by just adding a source and remote backup catalog using default parameters.

If your plan is to use RsyncGUI as your main tool for backup of files, please investigate and understand the limits of it. RsyncGUI is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## Old version of rsync

The default version of `rsync` in macOS is old (version 2.6.9, [protocol](https://rsync.samba.org/how-rsync-works.html) version 29). Version [2.6.9](https://download.samba.org/pub/rsync/src/rsync-2.6.9-NEWS) was released in nov 2006. The current release of rsync is version [3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) protocol 31 released 28 January 2018.

Utilizing **snapshots** in RsyncGUI is **not possible** due a bug in default version version 2.6.9 of rsync. It is not allowed because of the macOS sandbox, to execute an updated version of rsync in e.g `/usr/local/bin`. Utilizing **scheduled** task is also not implemented in RsyncGUI.

If you need either of them, please use [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX).

## Version 2.0.1

This version is approved for release on Apple Mac Store 15 April 2020.

- fixed a bug in abort task

## Version 2.0.0

This version is approved for release on Apple Mac Store 26 March 2020.

- batch is replaced with multiple selection of rows for executing
- minor GUI tweaks and cleanup

## Version 1.9.1

This version is approved for release on Apple Mac Store 27 February 2020.

- a few minor fixes

## Version 1.9.0

This version is approved for release on Apple Mac Store 18 February 2020.

- redesign of the Restore view
- some bugfixes

## Version 1.8.9

This version is approved for release on Apple Mac Store 28 January 2020.

- a few enhancements and fixes
- select other profile from Synchronize view

## Version 1.8.5

This version is approved for release on Apple Mac Store 22 December 2019.

- a few bugfixes
- cleanup of GUI
- new task `syncremote` which synchronize a remote source to local storage on Mac, the task require a remote server

## Version 1.8.1

This version is approved for release on Apple Mac Store 9 November 2019.

- a few internal updates and fixes

## Version 1.8.0

This version is approved for release on Apple Mac Store 24 October 2019.

- updated restore function
- refactor and cleanup in code
- fixed a couple of bugs

## Version 1.7.2

This version is approved for release on Apple Mac Store 7 September 2019.

- a few bugfixes

## Version 1.7.0

This version is approved for release on Apple Mac Store 29 August 2019.

The major part in this version are refactor and cleanup in code. Refactor is mainly for decoupling of code and make RsyncGUI easier for maintenance. I am also deleting not used code. The command `wc  -l *.swift` in the source catalog of RsyncGUI counts number of lines and swift classes and structs. There are about 200 classes and 12,600 lines of code in RsyncGUI now.

- fixed a couple of memory leaks
- a few GUI adjustments
- fixed a bug in delete logs and save logs to permanent store
- some adjustments in search and sort (in logs and all profiles)
- refactor of code and cleanup

## Version 1.6.0

This version is approved for release on Apple Mac Store 2 August 2019.

- some GUI adjustments
- fixed a bug in delete logs and save logs to permanent store
- some adjustments in search and sort (in logs and all profiles)

## Version 1.5.0

This version is approved for release on Apple Mac Store 27 June 2019.

- fixed some memory leaks
- this is primary a maintenance release, fixed some bugs and cleanup in code

## Version 1.1.0

This version is approved for release on Apple Mac Store 4 April 2019.

- quit RsyncGUI by red button upper left main window
- RsyncGUI center itself in screen when started
- view all profiles and configurations by menu button (moved from tab view)
- backup now and automatic backup my be executed from any view (tab) by menu buttons or shortcuts
- clean up of code and some bugfixes
- configuration is available by shortcut `⌘,` (Preferences)
- built by last release of Xcode 10.2
- removed code for snapshots (due to stock version of rsync in macOS)

## Version 1.0.1

Version 1.0.1 is released 4 February 2019. Some minor bugfixes after initial release.

## Version 1.0.0

The app is [released](https://itunes.apple.com/us/app/rsyncgui/id1449707783?l=nb&ls=1&mt=12) on Apple Mac App Store 24 January 2019.
