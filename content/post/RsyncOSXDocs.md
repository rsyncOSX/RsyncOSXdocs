+++
author = "Thomas Evensen"
title = "How to use RsyncOSX"
date = "2020-04-24"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["summary"]
categories = ["general information"]
lastmod = "2020-12-24"
+++
RsyncOSX is a GUI ontop of the command line utility `rsync`, no more no less. Rsync is a file-based tool for transferring and synchronization of files. RsyncOSX supports both synchronize and snapshot tasks. There is no custom solution for the synchronized archive. And you can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

All releases are [signed and notarized](/post/notarized/).

- RsyncOSX is compiled with support for **macOS Catalina** and **macOS Big Sur** only
  - the latest version is [released here](https://github.com/rsyncOSX/RsyncOSX/releases)
- RsyncOSX is built as [Universal macOS Binary](https://developer.apple.com/documentation/xcode/building_a_universal_macos_binary).

RsyncOSX can also be installed by homebrew
```bash
brew install --cask rsyncosx
```

## The changelog

There is a [changelog](/post/changelog/). Also please see info about [the latest version of rsync to install.](/post/rsync/) Before commencing use of RsyncOSX [there are a few important words to read](/post/important/).

## How to setup remote servers

Utilizing RsyncOSX to synchronize files to remote servers requires some setup. There are two options to setup [passwordless logins](/post/remotelogins/). The advised setup is by utilizing ssh-keys.

- [setup by ssh-keys](/post/ssh/)
- [rsync daemon setup](/post/rsyncdaemon/)

Snapshots is **not** possible with rsync daemon setup.

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

## User configuration

There are a few [user selected options](/post/userconfiguration/).

## RsyncOSX config files

Where does RsyncOSX [stores the config files](/post/configfiles/)?

## Compile

And there is some info about [how to compile RsyncOSX](/post/compile/).
