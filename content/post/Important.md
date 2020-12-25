+++
author = "RsyncOSX"
title = "Important info about using RsyncOSX"
date = "2020-04-23"
description = "Important info about using RsyncOSX"
tags = ["important"]
categories = ["general information"]
lastmod = "2020-12-25"
+++
RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of `rsync` to synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from those remote servers.

The UI can for users who dont know rsync, be difficult or complex to understand. It is not required to know `rsync` but it will ease the use and understanding of RsyncOSX. But it is though, possible to use RsyncOSX by just adding a source and remote backup catalog using default parameters. RsyncOSX supports **synchronize** and **snapshots** of files.

## RsyncOSX as your main tool for backup

If your plan is to use RsyncOSX as your main tool for backup of files, please investigate and understand the limits of it. RsyncOSX is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## The --delete parameter

Caution about RsyncOSX and the `--delete` parameter. The parameter is a default parameter. The parameter instructs rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source.

Every time you add a new task to RsyncOSX, execute an estimation run (--dry-run) and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncOSX (rsync) will delete all files in the destination.
