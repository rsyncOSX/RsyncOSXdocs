+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Passwordless logins by ssh-keys - assisted by RsyncOSX."
tags = ["passwordless","ssh keypath and identity file"]
categories = ["remotelogins"]
description = "RsyncOSX can guide you in setting up passwordless login by ssh-keys."
lastmod = "2020-12-13"
+++
RsyncOSX utilizes user set ssh keypath and identityfile. The ssh parameter within the rsync command is if set by the user:

`-e  "ssh -i ~/.ssh_keypath/identityfile -p NN"` where:

- `-i` is the ssh keypath and identityfile
- `-p` is the port number ssh communicates through, default port 22

If global ssh parameters are set, it applies to **all configurations**. It is possible to set other ssh values on each task. There is a check and QA of ssh keypath and identityfile. When enabling user selected ssh keypath and identityfile please make sure it is in compliance with:

`~/.mynewsshcatalog/mynewkey`

The prefix has to be `~` followed by a `/`. If not adding the prefix RsyncOSX will automatically add it for you. It is not required to be a `.` catalog. The check verify that the ssh keypath has the prefix `~` and at least two `/`.

The following ssh tools are used: `ssh-keygen` and `ssh-copy-id`. RsyncOSX only assist in setting up RSA based key.

The ssh functions assist in two methods:

- private and public ssh key pair based upon default ssh values for RSA based key `~/.ssh/id_rsa`
- private and public ssh key pair based upon user selected values as `~/.ssh_rsyncosx/rsyncosx`

If creating a new public ssh key pair based upon default ssh values for RSA based key (1), RsyncOSX does not add any parameters to the rsync command because this is default values. Ssh parameters to the rsync command is only added if the second method is choosed.

The following is the command for creating a new, alternative private and public ssh key pair:

`ssh-keygen -t rsa -N "" -f ~/.ssh_rsyncosx/rsyncosx`

- `-t rsa ""` generates a RSA based key-pair
- `-N ""` sets no password
- where `~/.ssh_rsyncosx/rsyncosx` is set by the user


The following command copy the newly created public key to the server:

`ssh-copy-id -i /Users/thomas/.ssh_rsyncosx/rsyncosx -p NN user@server`

You can also setup the new ssh keypath and identityfile in a terminal window and after setup add the new ssh keypath and identityfile in Userconfig. RsyncOSX will automatically enable it when added in user config.

If you want RsyncOSX to assist in setting up please select the ssh tab, open Userconfig and add new ssh keypath and identityfile and ssh port number if other than 22.

![ssh](/images/RsyncOSX/master/ssh/ssh.png)

Setting ssh keypath and identityfile and ssh port number in Userconfig.

![ssh](/images/RsyncOSX/master/ssh/ssh1.png)

After closing the Userconfig select `Create keys` and RsyncOSX will do the magic. Select `Remote server`and RsyncOSX will add commands for copy and test the public key to remote server. Copy the commands and paste it into a terminal window for execution.

![](/images/RsyncOSX/master/userparameters/userparameters.png)

The user can also apply local ssh keypath and identityfile and ssh port, which rules the global settings, on each task.

Make sure that the new ssh catalog has the correct permissions. Open a terminal window and execute the following command.

`chmod 700 ~/.ssh_rsyncosx`
