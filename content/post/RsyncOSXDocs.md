+++
author = "RsyncOSX"
title = "About RsyncOSX"
date = "2020-04-24"
description = "Some start info about using RsyncOSX."
tags = ["info"]
categories = ["info", "userdocuments"]
images  = ["images/RsyncOSX/master/intro/main.png"]
+++

Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

 - [getting and installing RsyncOSX](/post/rsyncosx/)
 - [there is a changelog](/post/changelog/)
 - [some info about signing and notarizing of RsyncOSX](/post/notarized/)

Using RsyncOSX for synchronize files to **remote servers** [require to setup passwordless logins](/post/remotelogins/).

### Using RsyncOSX

The following are documents about using RsyncOSX:
- a short [intro to RsyncOSX](/post/intro/)
- [add configurations](/post/addconfigurations/)
- [executing single tasks](/post/singletask/)
  - also edit tasks and [add parameters to rsync](/post/userparameters//) from main view
- utilizing the [snapshot feature](/post/snapshots/)
- utilizing the [quick backup feature](/post/quickbackup/)
- [scheduling of tasks](/post/scheduletasks/)
- [restore of files](/post/restore/)
- some info about [logging execution of tasks](/post/logging/)
- some info about [user configuration](/post/userconfiguration/)
- for [automatic backups](/post/automatic/)
- where does RsyncOSX [stores the config files](/post/configfiles/)
- [the verify function](/post/verify/)

### Why use RsyncOSX (and rsync)?

There is one simple answer to the question and the answer is [rsync](https://en.wikipedia.org/wiki/Rsync). Rsync is a **rock solid, well proven, secure, fast, reliable** and **very accessible** command line tool across platforms. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:

- do single synchronize tasks, synchronize source and destination (backup)
- do snapshot tasks, previous snapshots are saved to restore previous versions and deleted files
  - there is also a plan for delete and keep snapshots
- do quick synchronize tasks, either single tasks or group of tasks
- do synchronize tasks utilizing predefined parameters to rsync to save changed and deleted files
- choose other version of rsync in user configuration if preferred
- set user defined parameters to rsync
- tasks may be organized in profiles
- execute either a full restore or restore of single files from remote storage
- do scheduling of tasks
  - once, daily or weekly schedules
- detailed logging of tasks, output from rsync may be copied to macOS clipboard
- tasks my be aborted at any time

### RsyncGUI, a Sandboxed version of RsyncOSX

RsyncOSX is also released as [RsyncGUI](https://itunes.apple.com/us/app/rsyncgui/id1449707783?l=nb&ls=1&mt=12) on Apple Mac App Store. RsyncGUI only utilize the stock version of rsync in macOS. Because of that the snapshots feature not available in RsyncGUI. Neither is scheduled backups.s

## My own NAS setup

I have setup up my own [NAS](/post/diynas/). I am doing backups by using RsyncOSX and sharing out disk by AFP and SMB.

## The Source

There are some documents about [the source code](/post/source/)
