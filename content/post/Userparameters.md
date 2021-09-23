+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "User selected rsync parameters"
tags = ["user rsync parameters"]
categories = ["rsyncparameters"]
description = "RsyncOSX allows the user to set parameters to rsync."
lastmod = "2020-07-16"
+++
See also [default parameters](/post/rsyncparameters) for info about default parameters and the ssh parameters (local). Rsync utilizes a ton of parameters. Parameters are normally constructed as:

- parameter=value
```bash
--exclude-from=/Volumes/home/user/exclude-list.txt
```
- parameter only
```bash
--stats
```
```bash
--dry-run
```
For a full list of parameters to rsync please see the [rsync docs](https://download.samba.org/pub/rsync/rsync.html).

## Add parameters

You can instruct rsync to save changed and deleted files in a separate backup catalog ahead of the change. This feature is utilized by setting the following parameters:
- parameter instructs rsync to save changed files
```bash
--backup
```
- parameter where to save changed or deleted files before rsync synchronize source and destination, RsyncOSX does suggest a value for the, but you might set it to whatever you want
```bash
--backup-dir
```
- **rsync daemon**: `::` enabling rsync daemon puts a double colon `::` in address parameter to rsync. It forces rsync to use the rsync daemon remote.

There are [two possible setup for using the rsync daemon](/post/rsyncdaemon/). Utilizing a rsync daemon setup does **not** encrypt the transfer between client and server. To encrypt the transfer require tunneling traffic in a ssh protocol, [see how to setup ssh passwordless logins](/post/remotelogins/).

![](/images/RsyncOSX/master/userparameters/userparameters.png)

## Suffix on changed and deleted files

Rsync can also set a time stamp as suffix on files. This might be useful if there are several revisions of files. The --suffix parameter set suffix on files, suffix can be set on files together with the --backup parameter. One suffix might rename files which are either deleted or replaced newer files with a trailing date and time stamp.

- sample suffix FreeBSD
```bash
--suffix=`date +'%Y-%m-%d.%H.%M'`
```
- sample suffix Linux
```bash
--suffix=_$(date +%Y-%m-%d.%H.%M)
```

I have experienced some variations regarding the suffix. If you want to use suffix you might try an alternative suffix if the above is not working as expected. If so is true use  instead. You just have to try and see what works

The parameters in picture (below) instructs rsync to save changed files in catalog ../backup_Directory (relative to destination catalog) and suffix the backup file with timestamps. The above is enabled or disabled by select the backup button. The user might change the backup catalog. The backup catalog can either be absolute path or relative path. Default backup catalog is ../backup_Directory.
