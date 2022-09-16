+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Latest version of rsync"
tags = ["rsync version"]
categories = ["general information"]
lastmod = "2020-12-13"
+++
The default [version 2.6.9 of rsync in macOS](https://download.samba.org/pub/rsync/NEWS#2.6.9) was released in nov 2006. And  there has been several fixes and releases since then. The news about [the current release of rsync is here](https://download.samba.org/pub/rsync/NEWS). Due to new features in rsync and dependency to shared libraries it is not possible to bundle the latest version together with RsyncOSX.

It is adviced to install rsync as part of Homebrew. In RsyncOSX select [user configuration](/post/userconfiguration/) and set path for optional version of rsync. Install [homebrew](https://brew.sh/) and install the latest version of rsync as part of homebrew. Execute the command

`brew install rsync`

to install the latest version of rsync.

## Snapshots

RsyncOSX supports [snapshots](/post/snapshots/) of files. Due to a bug in version 2.6.9 in rsync, the snapshot feature of RsyncOSX require to install the latest version of rsync.
