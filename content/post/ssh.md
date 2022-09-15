+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Passwordless logins by ssh-keys"
tags = ["passwordless"]

categories = ["remote servers"]

description = "RsyncOSX can guide you in setting up passwordless login by ssh-keys"
lastmod = "2020-04-16"
+++
RsyncOSX utilizes user set ssh keypath and identityfile. Default values for ssh are `~/.ssh/id_rsa` and portnumber `22`. It is not required to set your own values for key path and identityfile if default values are used. The ssh parameter within the rsync command is, if set by the user:

```bash
-e  "ssh -i ~/.ssh_keypath/identityfile -p NN"
```

where `-i ~/.ssh_keypath/identityfile` is the ssh keypath and identityfile and `-p NN` is the port number ssh communicates through, default port 22

## Ssh keypath and identityfile

How to set ssh keypath and identityfile in [the user configuration](/post/sshsettings/).

If global ssh parameters are set, it applies to all configurations. It is possible to set other ssh values on each task. There is a check of the ssh keypath and identityfile. When enabling user selected ssh keypath and identityfile please make sure it is in compliance with:

```bash
~/.mynewsshcatalog/mynewkey
```

The prefix has to be `~` followed by a `/`. RsyncOSX will verify that the ssh keypath is prefix by `~` and at least two `/` before saving the new keypath.

## Tools used

The following ssh tools are used: `ssh-keygen` and `ssh-copy-id`. RsyncOSX only assist in setting up RSA based key.

The ssh functions assist in two methods:

- private and public ssh key pair based upon default ssh values for RSA based key `~/.ssh/id_rsa`
- private and public ssh key pair based upon user selected values as `~/.ssh_rsyncosx/rsyncosx`

If creating a new public ssh key pair based upon default ssh values for RSA based key, RsyncOSX does not add any parameters to the rsync command because this is default values. Ssh parameters to the rsync command is only added if the second method is chosen.

The following commands for creating a new, alternative private and public ssh key pair:

```bash
cd
mkdir .ssh_rsyncosx
ssh-keygen -t rsa -N "" -f ~/.ssh_rsyncosx/rsyncosx
```

where

- `-t rsa ""` generates a RSA based key-pair
- `-N ""` sets no password
- and `~/.ssh_rsyncosx/rsyncosx` is set by the user

The following command copy the newly created public key to the server:

```bash
ssh-copy-id -i /Users/thomas/.ssh_rsyncosx/rsyncosx -p NN user@server
```

You can also setup the new ssh keypath and identityfile in a terminal window and after setup add the new ssh keypath and identityfile in Userconfig. RsyncOSX will automatically enable it when added in user config.

The user can also apply local ssh keypath and identityfile and ssh port, which rules the global settings, on each task.

Make sure that the new ssh catalog has the correct permissions. Open a terminal window and execute the following command.

```bash
chmod 700 ~/.ssh_rsyncosx
```
