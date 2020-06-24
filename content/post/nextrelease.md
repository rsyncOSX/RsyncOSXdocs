+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Next release of RsyncOSX."
tags = ["nextrelease"]
categories = ["changelog"]
description = "What is in next release of RsyncOSX?"
+++
There are som changes to how the ssh part of RsyncOSX is implemented. First of all it is enabled a global, user selected ssh keypath and identity file. If utilized the global values is set in user config. And the global values only applies to tasks with remote servers.

Others changes to the ssh part is only supporting rsa based creation of ssh keypair. The user can of course create a new key and just tell RsyncOSX where the new key is.
![](/images/RsyncOSX/master/nextversion/globalssh.png)
A global value can be overridden by a local set value.
![](/images/RsyncOSX/master/nextversion/localssh.png)
If enabling monitoring, RsyncOSX monitor the network connection on tasks with remote services. The monitoring is only valid during execution of the task. If there is discovered a network drop an interrupt signal is sent to the active task and it stops with an errormessage (in log).

In the user configuration ssh keypath, identity file, ssh port and select monitoring on/off are new options.
![](/images/RsyncOSX/master/nextversion/monitorandssh.png)
New version of rsync is released. RsyncOSX is verified working with latest version.
![](/images/RsyncOSX/master/nextversion/newversionrsync.png)
