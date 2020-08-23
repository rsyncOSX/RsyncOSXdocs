+++
author = "RsyncOSX"
title = "How to use RsyncOSX"
date = "2020-04-24"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["summary"]
categories = ["general information"]
lastmod = "2020-08-07"
+++
RsyncOSX is a GUI ontop of the command line utility `rsync`, no more no less. Rsync is a file-based tool for transferring and synchronization of files. RsyncOSX supports both synchronize and snapshot tasks. There is no custom solution for the synchronized archive. And you can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files. And there [is a short about me](/about).

From version 6.4.2, RsyncOSX will be compiled with support for **macOS Mojave 10.14 - latest version**.  Version 6.4.0 of RsyncOSX is the last version which is compiled with support for macOS El Capitan 10.11 - macOS Catalina 10.15.

## Some words about RsyncOSX

RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of rsync to synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from those remote servers.

The UI can for users who dont know rsync, be difficult or complex to understand. It is not required to know rsync but it will ease the use and understanding of RsyncOSX. But it is though, possible to use RsyncOSX by just adding a source and remote backup catalog using default parameters.

RsyncOSX supports synchronize and snapshots of files.

RsyncOSX as your main tool for backup
|---|
If your plan is to use RsyncOSX as your main tool for backup of files, please investigate and understand the limits of it. RsyncOSX is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## The --delete parameter

Caution about RsyncOSX and the `--delete` parameter. The `--delete` is a default parameter. The parameter instructs rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source.

Every time you add a new task to RsyncOSX, execute an estimation run (--dry-run) and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncOSX (rsync) will delete all files in the destination.

## Changelog

There is [a changelog](/post/changelog/).

## Installing RsyncOSX

It is easy to download and install RsyncOSX. Download the .dmg file and drag the application to the folder you want to install in, default is `/Applications`. The application is signed and notarized by Apple.

 - [getting and installing RsyncOSX](/post/rsyncosx/)
 - [signing and notarizing of RsyncOSX](/post/notarized/)

## Remote servers

Using RsyncOSX for synchronize files to remote servers require some setup.

- there are [two options to setup passwordless logins](/post/remotelogins/)
  - the preferred [setup by ssh keys](/post/ssh/)
  - a rsync [daemon setup](/post/rsyncdaemon/)

Snapshot is not possible with rsync [daemon setup](/post/rsyncdaemon/).

## Add and execute single tasks

It is easy to add a first configuration and execute your first synchronize task.

- [add configurations](/post/addconfigurations/)
- [executing single tasks](/post/singletask/)

## Parameters to rsync

Rsync has a ton of parameters. In user selected parameters you can add your own additional parameters to rsync. There is also a set of default rsync parameters.

- [user selected parameters](/post/userparameters/)
- [default parameters](/post/rsyncparameters)

## Snapshots, quick backup and scheduling

Snapshot is an effective method for saving changes and deleted files. You can also execute a group of tasks. If you want to schedule daily or weekly synchronize or snapshot tasks, add a schedule in RsyncOSX and execute by the menu app.

- utilizing the [snapshot feature](/post/snapshots/)
- utilizing the [quick synchronize feature](/post/quickbackup/)
- [automatic backups](/post/automatic/)
- [scheduling of tasks](/post/scheduletasks/)

## Restore

Sometimes you need to restore files. Either execute a full restore or file by file.

- [restore of files](/post/restore/)

## Logging, configuration, config files, verify

There are some info about logging and where RsyncOSX store files. There are a few user selected options. And sometimes you should execute a verify of synchronized files.

- some info about [logging execution of tasks](/post/logging/)
- some info about [user configuration](/post/userconfiguration/)
- where does RsyncOSX [stores the config files](/post/configfiles/)
- the [verify function](/post/verify/)

## Intro and video

There is a [short intro to RsyncOSX](/post/intro/) and there are two short YouTube videos of RsyncOSX:

- [how to get and install RsyncOSX](https://www.youtube.com/watch?v=d-srHjL2F-0)
- adding and executing the first backup (old video - to be replaced)

## Source code and compile

And there is some info about the [source code and how to compile RsyncOSX](/post/source).
