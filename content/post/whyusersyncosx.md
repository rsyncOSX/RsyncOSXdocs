+++
author = "RsyncOSX"
title = "Why use RsyncOSX?"
date = "2020-04-23"
description = "Why should you use rsync and RsyncOSX."
tags = ["why rsyncosx"]
categories = ["general information"]
+++
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

### RsyncGUI - a Sandboxed version of RsyncOSX

RsyncOSX is also released as [RsyncGUI](https://itunes.apple.com/us/app/rsyncgui/id1449707783?l=nb&ls=1&mt=12) on Apple Mac App Store. RsyncGUI only utilize the stock version of `rsync` in macOS. Because of that the snapshots feature is not available in RsyncGUI. Neither is scheduled backups.

### My own NAS setup

I have setup up my own [NAS](/post/diynas/). I am doing backups by using RsyncOSX and sharing out disk by AFP and SMB.
