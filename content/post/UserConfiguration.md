+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "User configuration"
tags = ["userconfig"]
categories = ["general information"]
astmod = "2020-08-24"
+++
There are a few parameters to choose in user configuration. Parameters are saved to permanent store.

{{< image src="/images/RsyncOSX/master/userconfig/user.png" alt="" position="center" style="border-radius: 8px;" >}}

## Rsync

 - v3.2.x rsync - set optional path if NOT by Homebrev
   	- any version of rsync should work, but only version 2.6.9 and 3.2.x are tested and verified
    - [utilizing the snapshot feature](/post/snapshots/) require version 3.2.x of rsync
- optional path for rsync:
    - if utilized version of rsync is **not** installed by Homebrew set path to rsync
- temporary path restore:
    - preset temporary path for restoring single files and catalogs
    - preset temporary path for a full restore

If there is a not valid rsync path is set an error is presented.

## Logging

Detailed logging on or off:

- if detailed logging is on all backup tasks are logged, if off only last date for task is updated in Synchronize view

## Halt on error

If RsyncOSX discover error in output from rsync, operation will terminate if checked. Normally this should **not be** checked.

## Logging to file

Logging is saved to permanent store:

- either minimum (last 10 lines) or full logging of output from rsync, be carful not logging everything, the log file might be big
- the log file can be inspected by open the output
- the log file is stored at

`$HOME/.rsyncosx/macserial/rsynclog.txt`

## Monitor network connection

RsyncOSX can monitor the network connection during execution of tasks. If a network connection is dropped during execution, RsyncOSX sends an interrupt signal to the task and it halts with an error.

## Ssh parameters (global)

The user can set a selected ssh keypath and identityfile. Default values for ssh are `~/.ssh/id_rsa` and portnumber `22`. It is not required to set if default values are used.

- portnumber, which ssh communicates through
- keypath + identityfile, user selected if other than default

If global values are set, this is what the ssh parameter within the rsync command looks like.

`-e  "ssh -i ~/.ssh_keypath/identityfile -p NN"`

where

`-i ~/.ssh_keypath/identityfile`

is the ssh keypath and identityfile and

`-p NN`

is the port number ssh communicates through, default port 22.

If global ssh parameters are set, it applies to **all** configurations. It is possible to set other ssh values on each task.

## Number of days

Number of days:

- in Synchronize view tasks older than number of days are marked red

## Environment

Enable environment:

It is possible to enter an environment variable to the process which executes the synchronize task. An example of such is :

`"SSH_AUTH_SOCK": "/Users/username/.gnupg/S.gpg-agent.ssh"`

## Backup

The `Backup` function copies all configurations and logs as a backup to your

`$HOME/Documents/RsyncOSXcopy-$date-suffix`

Viewing the catalog in macOS Finder might show an empty catalog. The catalog is not empty, the configurations are saved as `.rsyncosx/macserialnumber` and Finder might not show `.` catalogs.
