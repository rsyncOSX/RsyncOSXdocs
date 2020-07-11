+++
author = "RsyncOSX"
title = "How to use RsyncOSX"
date = "2020-04-24"
description = "If you want some more info about RsyncOSX there are some resources here."
tags = ["summary"]
categories = ["general information"]
lastmod = "2020-07-11"
+++
RsyncOSX is a GUI ontop of the command line utility rsync, no more no less. Rsync is a file-based synchronization and backup tool. RsyncOSX supports both synchronize and snapshot tasks. There is no custom solution for the synchronized archive. And you can quit utilizing RsyncOSX (and rsync) at any time and still have access to all synchronized files.

## Changelog

There is [a changelog](/post/changelog/).

## Insalling RsyncOSX

It is easy to download and install RsyncOSX. Download the .dmg file and drag the application to the folder you want to install in, defaul is `/Applications`. The application is signed and notarized by Apple.

 - [getting and installing RsyncOSX](/post/rsyncosx/)
 - [signing and notarizing of RsyncOSX](/post/notarized/)

## Intro

- a short [intro to RsyncOSX](/post/intro/)

## Remote servers

Using RsyncOSX for synchronize files to remote servers require some setup.

- [there are two options to setup passwordless logins](/post/remotelogins/)
  - the preferred [setup by ssh keys](/post/ssh/)
  - a [rsync daemon setup](/post/rsyncdaemon/)

## Add and execute single tasks

- [add configurations](/post/addconfigurations/)
- [executing single tasks](/post/singletask/)

## Parameters to rsync

- [default parameters](/post/rsyncparameters)
- [user selected parameters](/post/userparameters/)

## Snapshots, quick backup and scheduling

- utilizing the [snapshot feature](/post/snapshots/)
- utilizing the [quick backup feature](/post/quickbackup/)
- [automatic backups](/post/automatic/)
- [scheduling of tasks](/post/scheduletasks/)

## Restore

- [restore of files](/post/restore/)

## Logging, configuration, config files, verify

- some info about [logging execution of tasks](/post/logging/)
- some info about [user configuration](/post/userconfiguration/)
- where does RsyncOSX [stores the config files](/post/configfiles/)
- [the verify function](/post/verify/)

## Source code and compile

- some info [about the source code and how to compile RsyncOSX](/post/source)
