---
layout: post
title:  "RsyncOSX default parameters"
permalink: RsyncParameters
---
RsyncOSX implements default parameters which are working fine for simple synchronize and restore tasks. The actual parameters used in tasks is depended upon executing rsync over **network connection** or not. Which standard parameters to use is computed during startup of application by reading the configuration file.

RsyncOSX does also facilitate user selected parameters. User selected parameters are stored by each task and set by user, see [user selected parameters](/Parameters).

## Standard parameters all tasks

The following parameters are applied to all tasks.

- `--archive`
	- ensures that all files are transferred with all attributes preserved
- `--verbose`
	- make rsync very outspoken, required for counting files in RsyncOSX
- `--delete`
	- delete all files at **destination** which are not in the **source**
	- **caution:** this parameter also applies when restoring files, always do a restore to a temporary restore catalog

## Standard parameters networked tasks only

The following parameters are for networked tasks only. A networked task is a task where destination is on a remote server, either on local LAN or on Internet.

- `--compress`
	- compress files before transmitting, applies only if remote server
- `-e ssh`
	- to ensure rsync tunnels traffic through a ssh-tunnel, applies only if there is a remote server
- `-e "ssh -p nn"`
	- choose another port `nn` if standard port 22 is not used, enable by setting port number in parameters, applies only if remote server
