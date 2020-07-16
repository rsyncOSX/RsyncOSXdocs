+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Rsync daemon setup"
tags = ["passwordless","rsync daemon"]
categories = ["remotelogins"]
description = "How to setup remote logins by rsync daemon. There are also two methods for setting up."
lastmod = "2020-07-16"
+++
It is advised to utilize ssh keys for setup of passwordless logins for rsync. But it is possible to setup rsync and passwordless login by utilize a rsync daemon setup.

With a few tweaks it is possible to get RsyncOSX working with rsync daemon. Be aware of not utilizing ssh, transfer of data is **not** encrypted. This is might not a problem on a local network, but I would not advise it on a public network (depends on what data is synchronized).

## Server side setup

The sample setup below is based upon a Ubuntu 19.04 server. How to get the rsync daemon up and running on the Ubuntu server is not part of this document. The rsync daemon on the server is setup to listen on port 873. It is also advised that the versions of rsync are equal on both client and server. There are two solutions for enabling a rsync daemon connection. For both setup of `/etc/rsyncd.conf` serverside is required.

The following lines are created on the server side in file: `/etc/rsyncd.conf`
```
pid file = /var/run/rsyncd.pid
lock file = /var/run/rsync.lock
log file = /var/log/rsync.log
port = 873
hosts allow = *
```
```
[files]
path = /home/public_rsync
comment = Backup files
read only = no
timeout = 300
auth users = thomas
secrets file = /etc/rsyncd.secrets
```

## Prefix username in RsyncOSX

Client side setup number one:

- prefix username `rsync://username`, remember the double `//`
- add a full path to the file with password, `--password-file=/Users/thomas/passord.txt`, set `chmod 600` on the password file
- delete the `-e ssh` parameter

With the above setup I was able to push and pull data utilizing RsyncOSX and a rsync daemon setup. The following commands for push and pull files are:

Push files (synchronize or backup)
```
/Users/thomas/bin/rsync --archive --verbose --compress --delete
--password-file=/Users/thomas/passord.txt --exclude=.git --dry-run
--stats /Users/thomas/GitHub/ rsync://thomas@10.0.0.41:/files/
```
Pull files (restore)
```
/Users/thomas/bin/rsync --archive --verbose --compress --delete
--password-file=/Users/thomas/passord.txt --exclude=.git --dry-run
--stats rsync://thomas@10.0.0.41:/files/ /Users/thomas/GitHub/
```
## Rsync daemon

Client side setup number two:

- enable the `rsync daemon`, it adds a double colon `::` to the rsync command string
- add a full path to the file with password, `--password-file=/Users/thomas/passord.txt`, set `chmod 600` on the password file
- delete the `-e ssh` parameter

![](/images/RsyncOSX/master/userparameters/userparameters.png)

Push files (synchronize or backup)
```
/Users/thomas/bin/rsync --archive --verbose --compress --delete
--password-file=/Users/thomas/passord.txt --exclude=.git --dry-run
--stats /Users/thomas/GitHub/ thomas@10.0.0.41::files/
```
