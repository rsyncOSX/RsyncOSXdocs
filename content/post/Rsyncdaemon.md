---
layout: post
title:  "Rsync daemon setup"
permalink: Rsyncdaemon
---
It is advised to utilize ssh keys for setup of password less logins for rsync. But it is possible to setup rsync and password less login by utilize a rsync daemon setup.

With a few tweaks it is possible to get RsyncOSX working with rsync daemon. Be aware of not utilizing ssh, transfer of data is **not** encrypted. This is might not a problem on a local network, but I would not advise it on a public network (depends on what data is synchronized).

The sample setup below is based upon a Ubuntu 19.04 server. How to get the rsync daemon up and running on the Ubuntu server is **not** part of this document. The rsync daemon on the server is setup to listen on port 873. It is also advised that the versions of rsync are equal on both client and server. There are two solutions for enabling a rsync daemon connection. For both setup of `/etc/rsyncd.conf` serverside is required.

The following lines are created on the server side in file: `/etc/rsyncd.conf`

```
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

The `files` in `[files]` is used in the setup.

### Prefix username in RsyncOSX

- prefix username `rsync://username`

![rsyncdaemon](/images/RsyncOSX/master/rsyncdaemon/rsyncdaemon1.png)

- add a full path to the file with password. Rsync will complain if it is not chmod 600. Also remove the `-e ssh` parameter.

![rsyncdaemon](/images/RsyncOSX/master/rsyncdaemon/rsyncdaemon2.png)

With the above setup I was able to push and pull data utilizing RsyncOSX and a rsync daemon setup. The following commands for push and pull files are:

Push files (synchronize or backup)

`/Users/thomas/bin/rsync --archive --verbose --compress --delete --password-file=/Users/thomas/passord.txt --exclude=.git --dry-run --stats /Users/thomas/GitHub/ rsync://thomas@10.0.0.41:/files/`

Pull files (restore)

`/Users/thomas/bin/rsync --archive --verbose --compress --delete --password-file=/Users/thomas/passord.txt --exclude=.git --dry-run --stats rsync://thomas@10.0.0.41:/files/ /Users/thomas/GitHub/`

### Double colon ::

By utilizing the double colon `::` is a slightly different syntax which does the same.  

![rsyncdaemon](/images/RsyncOSX/master/rsyncdaemon/rsyncdaemon3.png)
![rsyncdaemon](/images/RsyncOSX/master/rsyncdaemon/rsyncdaemon4.png)

Push files (synchronize or backup)

`/Users/thomas/bin/rsync --archive --verbose --compress --delete --password-file=/Users/thomas/passord.txt --exclude=.git --dry-run --stats /Users/thomas/GitHub/ thomas@10.0.0.41::files/`
