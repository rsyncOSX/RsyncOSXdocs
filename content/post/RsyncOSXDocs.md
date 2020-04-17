---
layout: post
title:  "About RsyncOSX"
permalink: AboutRsyncOSX
---
Rsync is a file-based synchronization and backup tool. There is no custom solution for the backup archive. You can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

 - [getting and installing RsyncOSX](/Install)
 - [there is a changelog](/Changelog)
 - [some info about signing and notarizing of RsyncOSX](/Notarized).

Using RsyncOSX for synchronize files to **remote servers** [require to setup passwordless logins](/Remotelogins).

### Using RsyncOSX

The following are documents about using RsyncOSX:
- a short [intro to RsyncOSX](/Intro)
- [add configurations](/AddConfigurations)
- [executing single tasks](/SingleTask)
  - also edit tasks and [add parameters to rsync](/Parameters) from main view
- utilizing the [snapshot feature](/Snapshots)
- utilizing the [quick backup feature](/Quickbackup)
- [scheduling of tasks](/ScheduleTasks)
- [restore of files](/Restore)
- some info about [logging execution of tasks](/Logging)
- some info about [user configuration](/UserConfiguration)
- for [automatic backups](/Automatic)
- where does RsyncOSX [stores the config files](/configfiles)
- [the verify function](/Verify)

### Why use RsyncOSX (and rsync)?

There is one simple answer to the question and the answer is [rsync](https://en.wikipedia.org/wiki/Rsync). Rsync is a **rock solid, well proven, secure, fast, reliable** and **very accessible** command line tool across platforms. RsyncOSX is just a GUI for executing rsync commands. Rsync is a command line tool with tons of parameters. Choosing the right parameter and to get the predicted result from rsync might be a challenge. RsyncOSX does the job for you. RsyncOSX also stores configurations in profiles and makes it easy to use different configurations.

The following features are implemented in RsyncOSX:

- do single synchronize tasks, synchronize source and destination (backup)
- do snapshot tasks, previous snapshots are saved to restore previous versions or deleted files
- do quick synchronize tasks, either single tasks or group of tasks, both synchronize and snapshot tasks
- do synchronize tasks utilizing predefined parameters to rsync to save changed and deleted files
- adding new tasks by drag and drop (for local volumes)
- tasks my be aborted at any time
- choose other version of rsync in user configuration
- user defined rsync parameters
  - the user can add parameters to rsync
- manage tasks in profiles
- either a full restore or restore of single files from remote storage
- scheduling of tasks
  - once, daily or weekly schedules
- detailed logging of tasks

### RsyncGUI, a Sandboxed version of RsyncOSX

RsyncOSX is also released as [RsyncGUI](https://itunes.apple.com/us/app/rsyncgui/id1449707783?l=nb&ls=1&mt=12) on Apple Mac App Store. RsyncGUI only utilize the stock version of rsync in macOS. Because of that the snapshots feature not available in RsyncGUI. Neither is scheduled backups.s

## My own NAS setup

I have setup up my own [NAS](/DIYNAS). I am doing backups by using RsyncOSX and sharing out disk by AFP and SMB.

## The Source

There are some documents about [the source code](/Source)
