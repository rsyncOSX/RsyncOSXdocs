+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Parameters to rsync"
tags = ["parameters"]
categories = ["rsync parameters"]
description = "RsyncOSX allows the user to set parameters to rsync."
lastmod = "2020-07-16"
+++

RsyncOSX implements default parameters which are working fine for simple synchronize and restore tasks. The actual parameters used in tasks are depended upon executing rsync over **network connection** or not. Which standard parameters to use is computed during startup of application by reading the configuration file. The user can also remove default parameters if required.

## Default rsync parameters

The following parameters are applied to all tasks:

- `--archive` ensures that all files are transferred with all attributes preserved
- `--verbose` make rsync very outspoken, required for counting files in RsyncOSX
- `--delete` delete all files at **destination** which are not in the **source**
	- this parameter also applies when restoring files, always do a restore to a temporary restore catalog

## Default rsync parameters networked tasks only

The following parameters are for networked tasks only. A networked task is a task where destination is on a remote server, either on local LAN or on Internet.

- `--compress` compress files before transmitting, applies only if remote server
- `-e ssh` to ensure rsync tunnels traffic through a ssh-tunnel, applies only if there is a remote server
- `-e "ssh -p nn"` choose another port nn if standard port 22 is not used, enable by setting port number in parameters, applies only if remote server

## Ssh parameters (local)

There are two parameters to set for ssh. The local ssh parameters overrides global ssh parameters set in the [user config](/post/userconfiguration/).

- ssh port, set if ssh uses other port than standard port `22`
- the ssh keypath and identity file, normally this is `.ssh/id_rsa`, set name only if other keypath and identity file to be used by ssh

## Adding parameters to rsync

Selecting the parameters tab enables adding new parameters to rsync.  Rsync utilizes a ton of parameters.

Parameters are normally constructed as:

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

### Backup parameters

You can instruct rsync to save changed and deleted files in a separate backup catalog ahead of the change. This feature is utilized by setting the following parameters:

- `--backup` parameter instructs rsync to save changed files
- `--backup-dir` parameter where to save changed or deleted files before rsync synchronize source and destination
	- RsyncUI does suggest a value for the `--backup-dir` but you might set it to whatever you want
- **rsync daemon**: `::` enabling rsync daemon puts a double colon `::` in address parameter to rsync. It forces rsync to use the rsync daemon remote.

There are [two possible setup for using the rsync daemon](/post/rsyncdaemon/). Utilizing a rsync daemon setup does **not** encrypt the transfer between client and server. To encrypt the transfer require tunneling traffic in a ssh protocol, [see how to setup ssh passwordless logins](/post/ssh/).

Default catalog for backup of `<catalog to synchronize>` relativ to the synchronized catalog is:
```bash
../backup_<catalog to synchronize>
```
### Suffix on changed and deleted files

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
