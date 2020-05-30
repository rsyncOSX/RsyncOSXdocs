+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Passwordless logins by ssh-keys - assisted by RsyncOSX."
tags = ["ssh"]
categories = ["remotelogins"]
description = "RsyncOSX can guide you in setting up passwordless login by ssh-keys."
+++
The RsyncOSX function for assisting in setting up ssh is changed in **release candidate version 6.3.1**. The new feature does not change anything for current users, but enables users to set their own ssh keypath and identity file. It is advised to utilize the release candidate if you want RsyncOSX to assist in setting up passwordless logins by ssh keys.

## Enable user selected ssk keypath and identityfile

There is a check and QA of ssh keypath and identityfile. When enabling user selected ssh keypath and identityfile please make sure it is in compliance with:

`~/.mynewsshcatalog/mynewkey`

The prefix has to be `~` followed by a `/`. If not adding the prefix RsyncOSX will automatically add it for you. It is not required to be a `.` catalog. The check verify that the ssh keypath has the prefix `~` and at least two `/`.

If global ssh parameters are set, it applies to all configurations. It is possible to set other ssh values on each task.

The release candidate version 6.3.1 adds a change in how RsyncOSX assist in setting up private and public ssh key pair. The current version of RsyncOSX does not allow the user to select an alternative private key to use with RsyncOSX. There is also a change in which ssh tools used in RsyncOSX to assist in setting up. The following ssh tools are used: `ssh-keygen` and `ssh-copy-id`.

Support for DSA key is removed. RsyncOSX only assist in setting up RSA based key.

The ssh functions assist in two methods:

1. private and public ssh key pair based upon default ssh values for RSA based key `~/.ssh/id_rsa`
2. private and public ssh key pair based upon user selected values as `~/.ssh_rsyncosx/rsyncosx`

If creating a new public ssh key pair based upon default ssh values for RSA based key (1), RsyncOSX does not add any parameters to the rsync command because this is default values. Ssh parameters to the rsync command is only added if the second method is choosed.

The following is the command for creating a new, alternative private and public ssh key pair:

`ssh-keygen -t rsa -N "" -f ~/.ssh_rsyncosx/rsyncosx`

where `~/.ssh_rsyncosx/rsyncosx` is set by the user. If using the release candidate please make sure it is the form `~/.mynewsshcatalog/mynewkey`. RsyncOSX checks before saving.

You can also setup the new ssh keypath and identityfile in a terminal window and after setup add the new ssh keypath and identityfile in Userconfig. RsyncOSX will automatically enable it when added in user config.

If you want RsyncOSX to assist in setting up please select the ssh tab, open Userconfig and add new ssh keypath and identityfile and ssh port number if other than 22.

![ssh](/images/RsyncOSX/master/ssh/ssh5.png)

Setting ssh keypath and identityfile and ssh port number in Userconfig.

![ssh](/images/RsyncOSX/master/ssh/ssh4.png)

After closing the Userconfig select `Create keys` and RsyncOSX will do the magic. Select `Remote server`and RsyncOSX will add commands for copy and test the public key to remote server. Copy the commands and paste it into a terminal window for execution.

![ssh](/images/RsyncOSX/master/ssh/ssh6.png)

The user can also apply local ssh keypath and identityfile and ssh port, which rules the global settings, on each task.

### The ssh parameter to rsync

This is what the ssh parameter within the rsync command looks like.

`-e  "ssh -i ~/.ssh_rsyncosx/rsyncosx -p 22"`

Make sure that the new ssh catalog has the correct permissions. Open a terminal window and execute the following command.

`chmod 700 ~/.ssh_rsyncosx`
