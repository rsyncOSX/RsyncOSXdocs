+++
author = "Thomas Evensen"
date = "2020-04-01"
title =  "First time start RsyncGUI"
tags = ["first start","rsyncgui"]
categories = ["general information"]
description = "What to do the first time you start RsyncGUI."
+++
This is a short guide what to do the first start of RsyncGUI, the Mac App Store version of RsyncOSX. This guide is primarily for executing synchronizing tasks to **remote servers**. It includes a link to how to setup passwordless login to remote server.

## Grant RsyncGUI access root home catalog

Access to remote servers from RsyncGUI is normally by utilizing ssh and ssh keys. There are more info about [the two options to setup passwordless logins](/post/remotelogins/). Default ssh keys are installed in `.ssh` catalog in your home catalog. If you dont have created ssh keys and `.ssh` catalog, the following are shown and you are not allowed to create default ssh keys.

![](/images/RsyncOSX/master/RsyncGUIfirststart/nossh.png)

Not allowed to create ssh keys du to no access to the `.ssh` catalog. You have to create a .ssh catalog and restart RsyncGUI to grant access to the newly created .ssh catalog. Ececute the following commands from a terminal window:

![](/images/RsyncOSX/master/RsyncGUIfirststart/norsakey.png)
```bash
cd
mdkir .ssh
chmod 700 .ssh
```
After executing the above commands, quit and restart RsyncGUI. The first action required when restarting RsyncGUI, is to grant access the root home catalog. Before choosing Allow, select root of the home catalog.

![](/images/RsyncOSX/master/RsyncGUIfirststart/homecatalog.png)

After allowing RsyncGUI to access your home catalog you are ready to add configurations. RsyncGUI will open with no tasks.

![](/images/RsyncOSX/master/RsyncGUIfirststart/initialstart.png)

Also check the SSH tab, it should look like this. If you dont plan to utilize remote servers access the `.ssh` catalog is **not** relevant.

![](/images/RsyncOSX/master/RsyncGUIfirststart/sshinitial.png)

Now you can let RsyncGUI assist in creating a ssh key pair. The default ssh key pairs are stored in `.ssh` catalog. See also info in link below about ssh, ssh keypath and identityfile.

### SSH keypath and identityfile

See more info about [ssh keypath and identityfile](/post/ssh/). If utilized the ssh keypath has to be in the form `~/.mynewsshcatalog/mynewkey`. Before saving the keypath, RsyncGUI checks the format. If it is not conformant, there is no saving.

The ssh keypath and identityfile has to be prefixed one `~` and must include at least two `/`.

## Logging

The user can set logging on of in userconfig. If there is an error, RsyncGUI logs the error from rsync. All logging to file is found in the following catalog:
```bash
~/Library/Containers/no.blogspot.rsyncgui/Data/Documents/rsynclog.txt`
```
Logfiles can also be viewed in view for rsync output.
