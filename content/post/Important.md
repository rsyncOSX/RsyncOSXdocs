+++
author = "Thomas Evensen"
title = "Important about RsyncOSX"
date = "2021-04-23"
description = "Important about RsyncOSX"
tags = ["important"]
categories = ["general information"]
lastmod = "2021-01-14"
+++
There are some important information about using RsyncOSX and rsync to learn if you are new to the command line tool rsync. RsyncOSX is only a GUI on top of rsync. It is rsync which does actual work, not RsyncOSX.

Please read the information below.

## The --delete parameter

The `--delete` parameter is a default parameter. The parameter instructs rsync too keep the **source** and **destination** in sync. Another word for it is: the parameter instructs rsync to **delete** all files in the destination which are not present in the source.

Every time you add a **new task** to RsyncOSX, execute an estimation run and inspect the result before executing a real run.

If you by accident set an empty catalog as source, RsyncOSX (rsync) will delete any files in the destination.

## RsyncOSX as your main tool for backup

RsyncOSX is not developed to be an easy to use synchronize and backup tool. The main purpose is to assist and ease the use of `rsync` to synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from those remote servers.

The UI of RsyncOSX can for users who dont know rsync, be difficult or complex to understand. Using RsyncOSX requires some knowledge of `rsync`. The main objective for RsyncOSX is to ease the use of `rsync`, not teach macOS users how to use `rsync`. That is beyond the scope of RsyncOSX. Setting the wrong parameters to rsync can result in deleted data. And RsyncOSX will not stop you for doing so. That is why it is very important to execute a simulated run (`--dry-run`) and inspect what happens before a real run.
