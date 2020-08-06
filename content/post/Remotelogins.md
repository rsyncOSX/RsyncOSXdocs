+++
author = "RsyncOSX"
date = "2020-04-17"
title =  "Remote servers and passwordless logins"
tags = ["passwordless"]
categories = ["remotelogins"]
description = "There are two ways to setup passwordless logins to remote servers."
lastmod = "2020-08-06"
+++
There are two ways to setup passwordless logins to a remote server and RsyncOSX supports both. It is advised to use ssh and ssh-keys, method one below, because the traffic is encrypted and it is considered more secure.

## Encrypted protocol by ssh and ssh-keys

Utilizing ssh enables passwordless logins to remote servers by ssh private and public key-pair.

Using [ssh-keys](https://wiki.archlinux.org/index.php/SSH_keys) is in general considered more safe than standard password solutions (single factor authentication). ssh-keys is based upon [public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).

- RsyncOSX can assist you [in setting up passwordless logins](/post/ssh/)

Rsync transfer data between client and server by tunneling transfer of data in an encrypted ssh tunnel.

## Not encrypted protocol by rsync daemon

There is also possible to setup RsyncOSX utilizing a **rsync daemon** setup for synchronizing files to remote servers.

- this is a special setup and require some [tweaking](/post/rsyncdaemon/)

Rsync is reading a local file with password information when connecting to the server side rsync daemon. The transfer of data between client and server is **not** encrypted.
