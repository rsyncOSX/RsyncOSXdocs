+++
author = "Thomas Evensen"
title = "Important info about using RsyncOSX"
date = "2020-04-23"
description = "Important info about using RsyncOSX"
tags = ["important"]
categories = ["general information"]
lastmod = "2021-01-14"
+++
RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of `rsync` to synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from those remote servers.

The UI of RsyncOSX can for users who dont know rsync, be difficult or complex to understand. Using RsyncOSX requires some knowledge of `rsync`. The main objective for RsyncOSX is to ease the use of `rsync`, not teach macOS users how to use `rsync`. That is beyond the scope of RsyncOSX. Setting the wrong parameters to rsync can result in deleted data. And RsyncOSX will not stop you for doing so. That is why it is very important to execute a simulated run (`--dry-run`) and inspect what happens before a real run.

RsyncOSX supports **synchronize** and **snapshots** of files.

## RsyncOSX as your main tool for backup

If your plan is to use RsyncOSX as your main tool for backup of files, please investigate and understand the limits of it. RsyncOSX is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## The --delete parameter

Caution about RsyncOSX and the `--delete` parameter. The parameter is a default parameter. The parameter instructs rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source.

Every time you add a new task to RsyncOSX, execute an estimation run (`--dry-run`) and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncOSX (rsync) will delete all files in the destination.
