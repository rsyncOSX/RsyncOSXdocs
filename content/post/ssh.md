+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Passwordless logins by ssh-keys - assisted by RsyncOSX."
tags = ["ssh"]
categories = ["remotelogins"]
description = "RsyncOSX can guide you in setting up passwordless login by ssh-keys."
+++
**Release candidate version 6.3.1:** the RsyncOSX function for assisting in setting up ssh is changed. For details see last on this page. The new feature does not change anything for current users, but enables users to set their own ssh keypath and identity file.

See last on this page for more info.

### Version 6.3.0

If you already have setup ssh utilizing ssh keys there is no need to follow the instructions below. RsyncOSX is depended upon passwordless logins for synchronizing data to remote servers. The instructions below only applies if passwordless login is not setup.

If utilizing RsyncOSX on local attached disks this does not apply.

The objective is to assist setting up [passwordless](/post/passwordlesslogin/) logins. Ssh does not provide any possibilities to pass password as parameter. Some actions to setup passwordless logins therefore require a terminal window for copy/paste commands for password prompt and execution of task.

### Local ssh keys

Select the Check button to verify if ssh keys are created or not. If there are no keys, either choose a rsa or dsa based private and public key pair or both (once a time).

![ssh](/images/RsyncOSX/master/ssh/ssh1.png)

- Rsa public key found (if file ~/.ssh/id_rsa.pub exists)
- Dsa public key found (if file ~/.ssh/id_dsa.pub exists)
- Create keys, either rsa or dsa based (by ssh-keygen)

Which key to create and use is for you to decide. I am using the rsa based key only.

### Create local ssh keys

Choosing a rsa based key and select Create keys. Local keys are created by ssh-keygen and saved in .ssh local catalog. The output shows information from the ssh-keygen tool. If creation of local key is OK the output should be something like in view. And the Rsa public key found should be ticked on. Likewise for a dsa based key.

![ssh](/images/RsyncOSX/master/ssh/rsa.png)
![ssh](/images/RsyncOSX/master/ssh/dsa.png)

After both keys are created the Create keys button is disabled.

### Remote server

After local private and public ssh key pair is created choosing Remote server to select which remote server to setup. It is required to [add](/post/addconfigurations/) configuration before setting up passwordless logins.
- Ssh directory - copy and paste command in Terminal.app to create remote ~/.ssh catalog
- Scp rsa - copy and paste command in Terminal.app to secure copy public rsa key.
- Scp dsa - copy and paste command in Terminal.app to secure copy public dsa key

![ssh](/images/RsyncOSX/master/ssh/ssh2.png)

### Transfer public key to remote server

Next step is to manually create a remote .ssh catalog and scp (secure copy) the public key to remote server.

- Scp rsa - copy and paste command

The command
```
/usr/bin/scp /Volumes/Home/thomas/.ssh/id_rsa.pub thomas@10.0.0.57:.ssh/authorized_keys
```
copy the rsa public key ~/.ssh/id_rsa.pub to remote server as file ~/.ssh/authorized_keys

- Scp dsa - copy and paste command

The command
```
/usr/bin/scp /Volumes/Home/thomas/.ssh/id_dsa.pub thomas@10.0.0.57:.ssh/authorized_keys2
```
copy the dsa public key ~/.ssh/id_dsa.pub to remote server as file ~/.ssh/authorized_keys2

After public key(s) are copied it is important to set correct permissions on remote public key files. The correct permissions are set by: chmod 700 means owner can read, write and execute on ./ssh catalog and chmod 600 on .ssh/authorized_keys means owner can read and write file.

- Check rsa - selecting button set correct mode on file and catalog
- Check dsa - as above but for the dsa public key

![ssh](/images/RsyncOSX/master/ssh/ssh3.png)

## Release candidate version 6.3.1

There is a check and QA of ssh keypath and identityfile. When enabling user selected ssh keypath and identityfile please make sure it is in compliance with:

`~/.mynewsshcatalog/mynewkey`

The prefix has to be `~/`. If not adding the prefix RsyncOSX will automatically add it for you. It is not required to be a `.` catalog.

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
