+++
author = "RsyncOSX"
title = "How to use RsyncOSX"
date = "2020-04-24"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["documents"]
categories = ["general information","summary"]
+++
#### What is RsyncOSX?

RsyncOSX is a GUI ontop of the command line utility rsync, no more no less. Rsync is a file-based synchronization and backup tool. RsyncOSX supports both synchronize and snapshot tasks. There is no custom solution for the synchronized archive. And you can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

 - [getting and installing RsyncOSX](/post/rsyncosx/)
 - [there is a changelog](/post/changelog/)
 - [signing and notarizing of RsyncOSX](/post/notarized/)

![](/images/RsyncOSX/master/intro/main.png)

#### Remote servers

Using RsyncOSX for synchronize files to remote servers require some setup. It is not possible to add login credentials during execution of any tasks.

- [there are two options to setup passwordless logins](/post/remotelogins/)
- the preferred [setup by ssh keys](/post/ssh/)
- and a [rsync daemon setup](/post/rsyncdaemon/)

#### Intro

- a short [intro to RsyncOSX](/post/intro/)

#### Add and execute single tasks
- [add configurations](/post/addconfigurations/)
- [executing single tasks](/post/singletask/)

#### Parameters to rsync
- parameters to rsync
  - [default parameters](/post/rsyncparameters)
  - [user selected parameters](/post/userparameters/)

#### Snapshots, quick backup and scheduling
- utilizing the [snapshot feature](/post/snapshots/)
- utilizing the [quick backup feature](/post/quickbackup/)
- [automatic backups](/post/automatic/)
- [scheduling of tasks](/post/scheduletasks/)

#### Restore
- [restore of files](/post/restore/)

#### Logging, configuration, config files, verify
- some info about [logging execution of tasks](/post/logging/)
- some info about [user configuration](/post/userconfiguration/)
- where does RsyncOSX [stores the config files](/post/configfiles/)
- [the verify function](/post/verify/)

#### Source code and compile
- some info [about the source code and how to compile RsyncOSX](/post/source)
