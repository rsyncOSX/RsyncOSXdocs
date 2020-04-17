---
layout: post
title:  "Menuapp"
permalink: Menuapp
---
This is the `menu app` (RsyncOSXsched.app) for executing scheduled tasks in RsyncOSX. Scheduled tasks are added in RsyncOSX. Quit RsyncOSX and let the menu app take care of executing the scheduled tasks. RsyncOSX does **not** execute scheduled tasks. Scheduled tasks are only added and deleted in RsyncOSX.

The `menu app` can be started from RsyncOSX. If the `menu app` is installed in other catalog than `/Applications`, alternative catalogs has to be set in userconfiguration.

![](/images/RsyncOSX/master/menuapp/userconfig.png).

The `menu app` submits a notification when a scheduled tasks are completed. A scheduled task is either of type `once`, `daily` or `weekly`. If there are tasks waiting to execute the status light will be green.

![](/images/RsyncOSX/master/menuapp/menuapp1.png)

There is a minimal logging in the menu app. The menu app logs the major actions within the menu app.

![](/images/RsyncOSX/master/menuapp/menuapp3.png)

Active scheduled tasks.

![](/images/RsyncOSX/master/menuapp/menuapp2.png)
