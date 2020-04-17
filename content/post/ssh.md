---
layout: post
title:  "Passwordless logins by ssh-keys"
permalink: ssh
---

If you already have setup ssh utilizing ssh keys there is no need to follow the instructions below. RsyncOSX is depended upon passwordless logins for synchronizing data to remote servers. The instructions below only applies if passwordless login is not setup.

If utilizing RsyncOSX on local attached disks this does not apply.

The objective is to assist setting up [passwordless](/PasswordlessLogin) logins. Ssh does not provide any possibilities to pass password as parameter. Some actions to setup passwordless logins therefore require a terminal window for copy/paste commands for password prompt and execution of task.

### Local ssh keys

Select the `Check` button to verify if ssh keys are created or not. If there are no keys, either choose a `rsa` or `dsa` based private and public key pair or both (once a time).

![ssh](/images/RsyncOSX/master/ssh/ssh1.png)

- `Rsa public key found` (if file `~/.ssh/id_rsa.pub` exists)
- `Dsa public key found` (if file `~/.ssh/id_dsa.pub` exists)
- `Create keys`, either rsa or dsa based (by `ssh-keygen`)

Which key to create and use is for you to decide. I am using the rsa based key only.

### Create local ssh keys

Choosing a `rsa` based key and select `Create keys`. Local keys are created by `ssh-keygen` and saved in `.ssh` local catalog. The output shows information from the `ssh-keygen` tool. If creation of local key is OK the output should be something like in view. And the `Rsa public key found` should be ticked on. Likewise for a `dsa` based key.

![ssh](/images/RsyncOSX/master/ssh/rsa.png)
![ssh](/images/RsyncOSX/master/ssh/dsa.png)

After both keys are created the `Create keys` button is disabled.

### Remote server

After local private and public ssh key pair is created choosing `Remote server` to select which remote server to setup. It is required to [add](/AddConfigurations) configuration before setting up passwordless logins.
- `Ssh directory` - copy and paste command in Terminal.app to create remote `~/.ssh` catalog
- `Scp rsa` - copy and paste command in Terminal.app to secure copy public rsa key.
- `Scp dsa` - copy and paste command in Terminal.app to secure copy public dsa key
![ssh](/images/RsyncOSX/master/ssh/ssh2.png)

### Transfer public key to remote server

Next step is to manually create a remote `.ssh` catalog and `scp` (secure copy) the public key to remote server.

- `Scp rsa` - copy and paste command

The command `/usr/bin/scp /Volumes/Home/thomas/.ssh/id_rsa.pub thomas@10.0.0.57:.ssh/authorized_keys` copy the rsa public key `~/.ssh/id_rsa.pub` to remote server as file `~/.ssh/authorized_keys`

- `Scp dsa` - copy and paste command

The command `/usr/bin/scp /Volumes/Home/thomas/.ssh/id_dsa.pub thomas@10.0.0.57:.ssh/authorized_keys2` copy the dsa public key `~/.ssh/id_dsa.pub` to remote server as file `~/.ssh/authorized_keys2`

After public key(s) are copied it is important to set correct permissions on remote public key files. The correct permissions are set by: `chmod 700` means owner can read, write and execute on `./ssh` catalog and `chmod 600` on `.ssh/authorized_keys` means owner can read and write file.

- `Check rsa` - selecting button set correct mode on file and catalog
- `Check dsa` - as above but for the dsa public key

![ssh](/images/RsyncOSX/master/ssh/ssh3.png)
