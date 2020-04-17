---
layout: post
title:  "First time start RsyncGUI"
permalink: RsyncGUIfirststart
---
This is a short guide what to do when first start of **RsyncGUI**, the Mac App Store version of RsyncOSX. This guide is primarily for executing synchronizing tasks to **remote servers**. It includes how to setup passwordless login to remote server. RsyncGUI only support  default version of `rsync` which is included in macOS. The default version of `rsync` in macOS is old, version 2.6.9, protocol version 29 released in nov 2006. This version of `rsync` does not support snapshot tasks. If you want to utilize [snapshot tasks](/Snapshots) please use RsyncOSX instead.

If you plan only utilizing RsyncGUI on local attached volumes you can skip this guide.

### First start of RsyncGUI

The first action required when starting RsyncGUI for the first time is to allow RsyncGUI to access the root home catalog. Before choosing `Allow` **select root** of the home catalog.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main2.png)

### If you plan utilizing remote servers

If you plan utilizing remote servers the following steps are required. It is only required if you have not setup the ssh private and public key-pair before. The private ssh keys are created and saved in `.ssh` catalog in your root home catalog.

### First steps setting up passwordless logins for rsync

See [manual setup of passwordless logins](/PasswordlessLogin) or the [RsyncOSX guide](/ssh) for info. Setting up passwordless logins is not required if this works before using RsyncGUI. It is **required** that ssh is utilizing the `.ssh` catalog in the users home root catalog.

### Create private and public ssh certificates

Ssh saves by default, private ssh-keys in `.ssh` catalog on root of your home catalog. RsyncGUI can assist you creating both the `.ssh` catalog and private and public key pair. If this is created **before** using RsyncGUI this action is not required.

Select the `Ssh` tab and create both keys.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main3.png)
![](/images/RsyncOSX/master/RsyncGUIfirststart/main4.png)

### Adding a synchronizing task

Then it is time to add a synchronizing task with a remote destination.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main5.png)

### Transferring public ssh certificates

After the synchronizing task is entered go back to the `Ssh` tab and let RsyncGUI assist you in transferring the public ssh-keys to the remote server.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main6.png)

Select the `Remote` button and choose the correct remote server. Choose `Terminal.app` to open a terminal and copy and paste the three lines in that order into the terminal.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main7.png)
![](/images/RsyncOSX/master/RsyncGUIfirststart/main8.png)

The last action to do is select the `Check rsa` and `Check dsa` to verify and set correct permissions on the remote `.ssh` catalog and public ssh-keys.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main9.png)

### Ready for first synchronizing tasks

Now you can do your first synchronizing task.

![](/images/RsyncOSX/master/RsyncGUIfirststart/main10.png)
