+++
author = "RsyncOSX"
title = "How to use RsyncOSX"
date = "2020-04-24"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["summary"]
categories = ["general information"]
lastmod = "2020-11-13"
+++
RsyncOSX is a GUI ontop of the command line utility `rsync`, no more no less. Rsync is a file-based tool for transferring and synchronization of files. RsyncOSX supports both synchronize and snapshot tasks. There is no custom solution for the synchronized archive. And you can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

- RsyncOSX is compiled with support for **macOS 10.15 Catalina** and **macOS 11.01 Big Sur** only
  - the latest version is [released here](https://github.com/rsyncOSX/RsyncOSX/releases)
  - RsyncOSX can also be installed by Homebrew `brew cask install rsyncosx`
- RsyncOSX is built as [Universal macOS Binary](https://developer.apple.com/documentation/xcode/building_a_universal_macos_binary).

All releases of RsyncOSX are [signed and notarized](/post/notarized/). And there [is a short about me](/about).

## The changelog

There is a [changelog](/post/changelog/). Also please see info about [the latest version of rsync in install](/post/rsync/).

## Some words about RsyncOSX

RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of `rsync` to synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from those remote servers.

The UI can for users who dont know rsync, be difficult or complex to understand. It is not required to know `rsync` but it will ease the use and understanding of RsyncOSX. But it is though, possible to use RsyncOSX by just adding a source and remote backup catalog using default parameters. RsyncOSX supports **synchronize** and **snapshots** of files.

RsyncOSX as your main tool for backup
|---|
If your plan is to use RsyncOSX as your main tool for backup of files, please investigate and understand the limits of it. RsyncOSX is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## The --delete parameter

Caution about RsyncOSX and the `--delete` parameter. The `--delete` is a default parameter. The parameter instructs rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source.

Every time you add a new task to RsyncOSX, execute an estimation run (--dry-run) and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncOSX (rsync) will delete all files in the destination.

## How to install RsyncOSX

It is easy to download and install RsyncOSX. Download the .dmg file and drag the application to the folder you want to install in, default is `/Applications`. The application is signed and notarized by Apple.

 - [getting and installing RsyncOSX](/post/rsyncosx/)
 - [signing and notarizing of RsyncOSX](/post/notarized/)

## How to setup remote servers

If you plan to use RsyncOSX for synchronize files to remote servers require some setup. There are [two options to setup passwordless logins](/post/remotelogins/). The advised setup is by utilizing ssh-keys.

- [setup by ssh keys](/post/ssh/)
- [daemon setup](/post/rsyncdaemon/)

Snapshot is not possible with rsync [daemon setup](/post/rsyncdaemon/).

## How to add and execute single tasks

It is easy to add a first configuration and execute your first synchronize task.

- [add configurations](/post/addconfigurations/)
- [executing single tasks](/post/singletask/)

## How to add parameters to rsync

Rsync has a ton of parameters. In user selected parameters you can add your own additional parameters to rsync. There is also a set of default rsync parameters.

- [user selected parameters](/post/userparameters/)
- [default parameters](/post/rsyncparameters)

## Snapshots, quick backup and scheduling

Snapshot is an effective method for saving changes and deleted files. You can also execute a group of tasks. If you want to schedule daily or weekly synchronize or snapshot tasks, add a schedule in RsyncOSX and execute by the menu app.

- utilizing the [snapshot feature](/post/snapshots/)
- utilizing the [quick synchronize feature](/post/quickbackup/)
- [scheduling of tasks](/post/scheduletasks/)

## How to restore

Sometimes you need to restore files. Either execute [a full restore or file by file](/post/restore/).

## Logging, configuration, config files, check

There are some info about logging and where RsyncOSX store files. There are a few user selected options. And sometimes you should execute a verify of synchronized files.

- some info about [logging execution of tasks](/post/logging/)
- some info about [user configuration](/post/userconfiguration/)
- where does RsyncOSX [stores the config files](/post/configfiles/)
- how to [check synchronized data](/post/check/)

## Intro and video

There are two short YouTube videos of RsyncOSX:

- [how to get and install RsyncOSX](https://youtu.be/d-srHjL2F-0)
- [adding and executing the first backup](https://youtu.be/vS5_rXdTtZ8)

## Compile

And there is some info about [how to compile RsyncOSX](/post/compile/).
