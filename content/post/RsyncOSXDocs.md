+++
author = "Thomas Evensen"
title = "How to use RsyncOSX"
date = "2022-05-09"
tags = ["overview"]
categories = ["general information"]
lastmod = "2022-05-09"
+++
RsyncOSX is a [signed and notarized](/post/notarized/) GUI on top of the command line utility `rsync`, which is a file based tool for synchronization of files. It is built as a Universal macOS Binary which means it runs natively on Apple Silicon and Intel based Mac computers.

- [RsyncOSX](https://github.com/rsyncOSX/RsyncOSX/releases) is compiled for **macOS Big Sur** and later
- the [changelog](/post/changelog/)

RsyncOSX can be installed by homebrew: `brew install --cask rsyncosx` or by download the [latest version](https://github.com/rsyncOSX/RsyncOSX/releases).

## First time

The first time RsyncOSX starts it presents a link to [important](/post/important/) information. There is also info about the latest [version of rsync](/post/rsync/) to install.

{{< image src="/images/RsyncOSX/master/start/start.png" alt="" position="center" style="border-radius: 8px;" >}}

The error in bottom of the view is only RsyncOSX complaining about not finding the default file for stored tasks. The error disappears as soon as the first task is added.

### Aborting a task

Please be aware it is an external task not controlled by RsyncOSX which executes the command line tool `rsync`. RsyncOSX is monitoring the task for progress and termination. The user can abort a task at any time. Please let the abort to finish and cleanup properly before starting a new task. It might take a few seconds. If not the apps might become unresponsive.

One of many advantages of utilizing `rsync` is that it can restart and continue the synchronize task from where it was aborted.

### Verify a new task

After adding [a task](/post/addconfigurations/), a double click on the new task will execute a simulated run or what is called a `dryrun`. Verify the output from rsync by opening the log, top left icon in sidebar of RsyncOSX, either ahead or after the simulated run. 

For more experienced users of rsync, select the new task and press the `Command` button. Copy and paste the `Synchronize` string into a terminal view. The rsync command includes the `dryrun` parameter as default within this view.

## Synchronize data

After [adding a task](/post/addconfigurations/) you are ready to execute a [synchronize data task](/post/singletask/).

**Always** verify, by a `dryrun`,  the result of a **new** task before executing it.

## Remote servers

Utilizing RsyncOSX to synchronize files to remote servers requires some setup. There are two options to setup [passwordless logins](/post/remotelogins/). The advised setup is by utilizing ssh-keys.

- by [ssh-keys](/post/ssh/)
- by [rsync daemon setup](/post/rsyncdaemon/)

Snapshots is **not** possible with rsync daemon setup.

## Add parameters to rsync

Rsync has a ton of parameters. In user selected parameters you can add your own additional parameters to rsync. There is also a set of default rsync parameters.

- default [parameters](/post/rsyncparameters)
- user selected [parameters](/post/userparameters/)

## Snapshots

[Snapshot is an effective method](/post/snapshots/) for saving previous versions of data and deleted files in case of a restore.

## Schedule tasks

By default the schedules part is **not** enabled, enable [scheduling of tasks](/post/scheduletasks/) in userconfig.

## Restore of files

Sometimes you need to [restore files](/post/restore/).

## User configuration

There are a few [user selected options](/post/userconfiguration/).

## RsyncOSX config files

Where does RsyncOSX [stores the config files](/post/configfiles/)?

## Compile

And there is some info about [how to compile RsyncOSX](/post/compile/).
