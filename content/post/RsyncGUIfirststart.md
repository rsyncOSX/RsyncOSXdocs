+++
author = "RsyncOSX"
date = "2020-04-01"
title =  "First time start RsyncGUI"
tags = ["first start","rsyncgui"]
categories = ["general information"]
description = "What to do the first time you start RsyncGUI."
+++
This is a short guide what to do the first start of RsyncGUI, the Mac App Store version of RsyncOSX. This guide is primarily for executing synchronizing tasks to **remote servers**. It includes how to setup passwordless login to remote server. RsyncGUI only support  default version of rsync which is included in macOS. The default version of rsync in macOS is old, version 2.6.9, protocol version 29 released in nov 2006. This version of rsync does not support snapshot tasks. If you want to utilize [snapshot tasks](/post/snapshots) please use RsyncOSX instead.

If you plan only utilizing RsyncGUI on local attached volumes you can skip this guide.

## Access root home catalog

The first action required when starting RsyncGUI for the first time is to allow RsyncGUI to access the root home catalog. Before choosing Allow **select root** of the home catalog.

![](/images/RsyncOSX/master/RsyncGUIfirststart/homecatalog.png)

After allowing RsyncGUI to access your home catalog you are ready to add configurations. RsyncGUI will open with no tasks.

![](/images/RsyncOSX/master/RsyncGUIfirststart/initialstart.png)

Also check the Ssh tab, it should look like this. If you dont plan to utilize Remote servers access the `.ssh`catalog is **not** relevant.

![](/images/RsyncOSX/master/RsyncGUIfirststart/sshinitial.png)

## If you plan utilizing remote servers

If you plan utilizing remote servers the following steps are required. It is only required if you have not setup the ssh private and public key-pair before. The private ssh keys are created and saved in .ssh catalog in your root home catalog.

See [how to setup passwordless logins](/post/remotelogins/) for info.

### SSH keypath and identityfile

See more info about [ssh keypath and identityfile](/post/ssh/). If utilized the ssh keypath has to be in the form `~/.mynewsshcatalog/mynewkey`. Before saving the keypath, RsyncGUI checks the format. If it is not conformant, there is no saving.

The ssh keypath and identityfile has to be prefixed one `~` and must include at least two `/`.

## Logging

The user can set logging on of in userconfig. If there is an error, RsyncGUI logs the error from rsync. All logging to file is found in the following catalog:

`~/Library/Containers/no.blogspot.rsyncgui/Data/Documents/rsynclog.txt`

Logfiles can also be viewed in view for rsync output.

## The --delete parameter

Caution about RsyncGUI and the `--delete` parameter. The `--delete` is a default parameter. The parameter instructs
rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source. Every time you add a new task to RsyncGUI, execute an estimation run `--dry-run` and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncGUI (rsync) will delete all files in the destination.
