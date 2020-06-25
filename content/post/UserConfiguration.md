+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "User configuration"
tags = ["userconfig"]
categories = ["general information"]
astmod = "2020-06-25"
+++
There are only a few parameters to choose in user configuration. Configurations are saved to permanent store. This applies for version 6.3.x and greater of RsyncOSX.

![](/images/RsyncOSX/master/userconfig/user.png)

## Rsync

 - 3.1.2, 3.1.3, 3.2.1 rsync - set optional path if **not** in /usr/local/bin
   	- any version of rsync should work, but only rsync  version 3.1.2, version 3.1.3 protocol version 31 and rsync  version 2.6.9  protocol version 29 are tested and verified
    - [utilizing the snapshot feature](/post/snapshots/) require either version 3.1.2, 3.1.3, 3.2.1 of rsync
- optional path for rsync:
    - if other version of rsync is installed in other path than /usr/local/bin it must be set here
- temporary path restore:
    - preset temporary path for restoring single files and catalogs
    - preset temporary path for a full restore

If there is a not valid rsync path is set an error is presented in bottom of user configuration. If there still is missing rsync in optional path no execution of tasks is allowed.

## Paths for RsyncOSX and RsyncOSXsched

- Automatic execution of local configurations
- path RsyncOSX
- path RsyncOSXsched

If both apps are installed in `/Applications` there is no need for setting paths.

Automatic execution of local configurations enables the menu app to automatically execute synchronize operations when local volumes are mounted.

## Logging

Detailed logging on or off
- if detailed logging is on all backup tasks are logged, if off only last date for task is updated in Synchronize view

## Halt on error

If RsyncOSX discover error in output from rsync, operation will terminate if checked. Normally this should not be checked.

## Logging to file

Logging is saved to permanent store.

- either minimum (last 10 lines) or full logging of output from rsync, be carful not logging everything, the log file might be big
- log file is Documents/rsynclog.txt

## Monitor network connection

On macOS 10.14 and later, RsyncOSX can monitor the network connection during execution of tasks. If a network connection is dropped during execution, RsyncOSX sends an interrupt signal to the task and it halts with an error.

## Check data when loading

- Check data

The schedule part is refactored. Select a configuration and all schedules are listed. Schedules can be stopped and deleted. Logs can be deleted. Logs are stored by configuration and schedule. There has been a bug in storing logs which creates more records than necessary. By setting check data, RsyncOSX will clean up. The check data flag is **not** persistent and have to be set each time.

## Ssh parameters (global)

The user can set a selected ssh keypath and identityfile. Default values for ssh are `~/.ssh/id_rsa` and portnumber `22`. It is not required to set if default values are used.

- portnumber, which ssh communicates through
- keypath + identityfile, user selected if other than default

If global values are set, this is what the ssh parameter within the rsync command looks like.

`-e  "ssh -i ~/.ssh_rsyncosx/rsyncosx -p NN"` where:

- `-i` is the ssh keypath and identityfile
- `-p` is the port number ssh communicates through, default port 22

If global ssh parameters are set, it applies to **all configurations**. It is possible to set other ssh values on each task.

## Number of days

Number of days
- in Synchronize view tasks older than number of days are marked red

## Environment

Enable environment

It is possible to enter an environment variable to the process which executes the synchronize task. An example of such is :

`"SSH_AUTH_SOCK": "/Users/username/.gnupg/S.gpg-agent.ssh"`
