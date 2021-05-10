+++
author = "Thomas Evensen"
date = "2020-04-16"
title =  "RsyncOSX default parameters"
tags = ["default rsync parameters"]
categories = ["rsyncparameters"]
description = "There are som default parameters to rsync."
lastmod = "2020-07-16"
+++
RsyncOSX implements default parameters which are working fine for simple synchronize and restore tasks. The actual parameters used in tasks are depended upon executing rsync over **network connection** or not. Which standard parameters to use is computed during startup of application by reading the configuration file. The user can also remove default parameters if required.

![](/images/RsyncOSX/master/userparameters/userparameters.png)

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

- ssh port, set if ssh uses other port than standard port 22
- the ssh keypath and identity file, normally this is `.ssh/id_rsa`, set name only if other keypath and identity file to be used by ssh

## User selected Parameters

There is also possible to add [user selected parameters](/post/userparameters/).
