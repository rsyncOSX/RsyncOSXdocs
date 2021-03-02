+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "screenshots next version"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-03-02"
+++
The UI will change as the development continues, but the overall structure of the new version will be like the views below The default view when starting the app. Select a new profile any time and the app reloads the data.

The screenshots are updated 2 March 2021.

![](/images/RsyncOSX/master/swiftui/start.png)

The start might be `Multiple tasks`. Choose `Estimate` and then `Execute` after estimation is completed. The estimation marks tasks with data for synchronizing. Or just go for all tasks, no estimation and execute direct. An example of how easy it is too create the UI is the [Estimation View](https://github.com/rsyncOSX/RsyncSwiftUI/blob/main/RsyncSwiftUI/Views/Multitask/EstimationView.swift). There are approx only 60 lines of code for the layout of the estimation view (below).

![](/images/RsyncOSX/master/swiftui/multiple.png)

If you want more control, select `Single task`. Choose either `Estimate` and `Execute` or `Now`, which executes without estimation.

![](/images/RsyncOSX/master/swiftui/single.png)

Viewing the actual rsync command and parameters to rsync for one task. The user can (when the app is released) set any setting to rsync. The `Copy` button copy the command to memory for possible paste it into a terminal view.

![](/images/RsyncOSX/master/swiftui/rsynccommand.png)

Within the `Add or edit` menu, either update an existing task or add new tasks.

![](/images/RsyncOSX/master/swiftui/addedit.png)

RsyncOSX supports snapshot tasks. It us important to administrate, delete, older snapshots not needed. RsyncOSX support a couple of plans to assist in which to keep and delete.

![](/images/RsyncOSX/master/swiftui/snapshot.png)
![](/images/RsyncOSX/master/swiftui/snapshottag.png)

Some user settings.

![](/images/RsyncOSX/master/swiftui/settings.png)

SSH settings and a few others.

![](/images/RsyncOSX/master/swiftui/ssh.png)
