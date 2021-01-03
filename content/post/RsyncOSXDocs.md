+++
author = "RsyncOSX"
title = "How to use RsyncOSX"
date = "2020-04-24"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["summary"]
categories = ["general information"]
lastmod = "2020-12-24"
+++
RsyncOSX is a GUI ontop of the command line utility `rsync`, no more no less. Rsync is a file-based tool for transferring and synchronization of files. RsyncOSX supports both synchronize and snapshot tasks. There is no custom solution for the synchronized archive. And you can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

- RsyncOSX is compiled with support for **macOS Catalina** and **macOS Big Sur** only
  - the latest version is [released here](https://github.com/rsyncOSX/RsyncOSX/releases)
  - RsyncOSX can also be installed by homebrew - `brew install --cask rsyncosx`
- RsyncOSX is built as [Universal macOS Binary](https://developer.apple.com/documentation/xcode/building_a_universal_macos_binary).

All releases of RsyncOSX are [signed and notarized](/post/notarized/). And there [is a short about me](/about).

## The changelog

There is a [changelog](/post/changelog/). Also please see info about [the latest version of rsync to install.](/post/rsync/)

## A few important words about RsyncOSX

Before commencing use of RsyncOSX [there are a few important words to read](/post/important/).

## How to setup remote servers

Utilizing RsyncOSX to synchronize files to remote servers requires some setup. There are two options to setup [passwordless logins](/post/remotelogins/). The advised setup is by utilizing ssh-keys.

- [setup by ssh-keys](/post/ssh/)
- [rsync daemon setup](/post/rsyncdaemon/)

Snapshot is not possible with [rsync daemon setup](/post/rsyncdaemon/).

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
