+++
author = "Thomas Evensen"
title = "Important"
date = "2021-04-23"
description = "Important about RsyncOSX"
tags = ["important"]
categories = ["general information"]
lastmod = "2021-01-14"
+++
If you are new to the command line tool `rsync` and RsyncOSX please read this information. RsyncOSX is a GUI only on top of the command line tool. It is `rsync` which does actual work, not RsyncOSX.

## The --delete parameter and new tasks

The `--delete` parameter is a *default parameter* set by RsyncOSX to `rsync`. The parameter instructs rsync too keep the *source* and *destination* in sync. The parameter instructs rsync to *delete* all files in the destination which are not present in the source. Every time you add a *new task* to RsyncOSX, execute an estimation run and inspect the result before executing a real run. If you by accident set an empty catalog as source, RsyncOSX (rsync) will delete all files in the destination.

Default parameters set by RsyncOSX to `rsync` can be disabled task by task. If you decide to disable a default parameter, be sure you understand what the result is. A disabled parameter can be enabled again.

## Aborting a task

Please be aware it is an external task not controlled by RsyncOSX, which executes the command line tool `rsync`. RsyncOSX is monitoring the task for progress and termination. The user can abort a task at any time. Please let the abort to finish and cleanup before starting a new task. It might take a few seconds. If not RsyncOSX might become unresponsive.

One of many advantages of utilizing `rsync` is that it can restart and continue the synchronize task from where it was aborted.

## RsyncOSX as your main tool for backup

RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of `rsync` to synchronize files on your Mac to remote FreeBSD and Linux servers or to a local attached disk. And of course restore files if required.

The UI of RsyncOSX can for users who dont know `rsync`, be difficult or complex to understand. The main objective is to ease the use of `rsync`, not teach macOS users how to use it. That is beyond the scope. Setting wrong parameters to rsync can result in deleted data. And RsyncOSX will not stop you for doing so. That is why it is very important to execute a simulated run (`--dry-run`) and inspect what happens before a real run.
