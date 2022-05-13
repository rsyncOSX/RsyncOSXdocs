+++
author = "Thomas Evensen"
title = "How to use RsyncOSX"
date = "2022-05-09"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["summary"]
categories = ["general information"]
lastmod = "2022-05-09"
+++
RsyncOSX is a [signed and notarized](/post/notarized/) GUI on top of the command line utility `rsync`, which is a file based tool for synchronization of files. It is built as a Universal macOS Binary which means it run natively on Apple Silicon and Intel based Mac computers.

- the [latest version](https://github.com/rsyncOSX/RsyncOSX/releases) of RsyncOSX is compiled for **macOS Big Sur** and later
- the [changelog](/post/changelog/)

RsyncOSX can also be installed by homebrew: `brew install --cask rsyncosx`.

## First start

The first time RsyncOSX starts it presents a link to [important words](/post/important/) about it. There is also info about [the latest version of rsync](/post/rsync/) to install.

{{< image src="/images/RsyncOSX/master/start/start.png" alt="" position="center" style="border-radius: 8px;" >}}

The error in bottom of the view is only RsyncOSX complaining about not finding the default file for stored tasks. The error disappears as soon as the first task is added.


## Add and execute your first task

It is easy to add and execute your first synchronize task.

- add [a task](/post/addconfigurations/)
- execute [a single task](/post/singletask/)

**Always** verify the result of a task before executing it.

## How to setup remote servers

Utilizing RsyncOSX to synchronize files to remote servers requires some setup. There are two options to setup [passwordless logins](/post/remotelogins/). The advised setup is by utilizing ssh-keys.

- by [ssh-keys](/post/ssh/)
- by [rsync daemon setup](/post/rsyncdaemon/)

Snapshots is **not** possible with rsync daemon setup.

## How to add parameters to rsync

Rsync has a ton of parameters. In user selected parameters you can add your own additional parameters to rsync. There is also a set of default rsync parameters.

- default [parameters](/post/rsyncparameters)
- user selected [parameters](/post/userparameters/)

## Snapshots and execute several tasks

Snapshot is an effective method for saving changes and deleted files. You can also execute a group of tasks.

- utilizing [the snapshot](/post/snapshots/) feature
- synchronize [several tasks](/post/severaltasks/)

## Schedule tasks

By default the schedules part is not enabled, enable the schedule part in the userconfig. The schedules is available by a button within the main view.

- scheduling of [tasks](/post/scheduletasks/)

## Restore of files

Sometimes you need to [restore files](/post/restore/).

## User configuration

There are a few [user selected options](/post/userconfiguration/).

## RsyncOSX config files

Where does RsyncOSX [stores the config files](/post/configfiles/)?

## Compile

And there is some info about [how to compile RsyncOSX](/post/compile/).
