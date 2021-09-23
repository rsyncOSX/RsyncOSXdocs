+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Rsync daemon setup"
tags = ["passwordless","rsync daemon"]
categories = ["remotelogins"]
description = "How to setup remote logins by rsync daemon. There are also two methods for setting up."
lastmod = "2020-07-16"
+++
With a few tweaks it is possible to get RsyncOSX working with rsync daemon. Be aware of not utilizing ssh, transfer of data is not encrypted. This is might not a problem on a local network, but I would not advise it on a public network. Also be aware of **snapshot is not possible** with a rsync daemon setup.

Setting up a rsync daemon setup require a server side setup and some tweaks in RsyncOSX.

## Server setup

The sample setup below is based upon a Ubuntu 19.04 server. How to get the rsync daemon up and running on the Ubuntu server is not part of this document. The rsync daemon on the server is setup to listen on port 873. It is also advised that the versions of rsync are equal on both client and server. There are two solutions for enabling a rsync daemon connection. For both setup of `/etc/rsyncd.conf` serverside is required.

The following lines are created on the server side in file: `/etc/rsyncd.conf`
```bash
pid file = /var/run/rsyncd.pid
lock file = /var/run/rsync.lock
log file = /var/log/rsync.log
port = 873
hosts allow = *

[files]
path = /home/public_rsync
comment = Backup files
read only = no
timeout = 300
auth users = thomas
secrets file = /etc/rsyncd.secrets
```

The file `/etc/rsyncd.secrets` stores the passwords for each user on the server side. Set `chmod 600` on the `/etc/rsyncd.secrets` file.

```bash
user1:password_for_user1
user2:password_for_user2
```
The rsync daemon has to be started on the server. There are several methods to automatically start the rsync daemon. For a test you can execute `sudo rsync --daemon` to start rsync as a daemon on the server.

## RsyncOSX setup

There are two methods in RsyncOSX to enable rsync daemon setup. One is to prefix the username and the second is to use a double colon. Both are demonstrated below.

## Prefix username in RsyncOSX

Within the edit view:

- prefix username `rsync://username`, remember the double `//`

![](/images/RsyncOSX/master/rsyncdaemon/edit.png)


Within the parameter view:

- in the parameter view, add a full path to the file with password, `--password-file=/Users/thomas/passord.txt`, remember to set `chmod 600` on the password file
- in the parameter view, delete the `-e ssh` parameter

## Enable the rsync daemon

All actions is within the parameter view:

- enable the `rsync daemon`, it adds a double colon `::` to the rsync command string
- add a full path to the file with password, `--password-file=/Users/thomas/passord.txt`, remember to set `chmod 600` on the password file
- delete the `-e ssh` parameter

![](/images/RsyncOSX/master/rsyncdaemon/rsyncdaemon.png)
