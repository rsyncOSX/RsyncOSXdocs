+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Some screenshots of next version"
tags = ["swiftui, nextversion"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-03-10"
+++
The UI will change as the development continues. But the overall structure and navigation will be like the views below. The screenshots and info are updated **10 March 2021**. There will probably be a testversion within a week or two.

## Error handling

The error handling is better in this version. If e.g rsync produces the word `error` in the output,  an alert will inform about it. If a validate of input, when adding new configurations, fails an alert will inform about the error. And so on...

![](/images/RsyncOSX/master/swiftui/error.png)

## Start

The default view when starting the app. Select a profile at any time and the app reloads the data. The start might be `Multiple tasks`. The main view informs about which version of rsync is utilized and if JSON or PLIST is used for storing configurations and schedules.

![](/images/RsyncOSX/master/swiftui/start.png)

## Multiple tasks

Choose `Estimate` and then `Execute` after estimation is completed. The estimation marks tasks with data for synchronizing. Or just go for all tasks, no estimation and execute direct. An example of how easy it is too create the UI is the [Estimation View](https://github.com/rsyncOSX/RsyncSwiftUI/blob/main/RsyncUI/Views/Multitask/EstimationView.swift). There are approx only 60 lines of code for the layout of the estimation view (below).

The view also includes a **delete function** for configurations.

![](/images/RsyncOSX/master/swiftui/multiple.png)

## Single task

If you want more control, select `Single task`. Choose either `Estimate` and `Execute` or `Now`, which executes without estimation.

![](/images/RsyncOSX/master/swiftui/single.png)

## Schedules

Adding schedules and deleting tasks and logs.

The following is work todo:

- some more QA and work is required

![](/images/RsyncOSX/master/swiftui/schedule.png)

## Parameters to rsync and the command

Viewing the actual rsync command and parameters to rsync for one task. The user can (when the app is released) set any parameter to rsync. The `Copy` button copy the actual rsync command (--dry-run) to memory for possible paste it into a terminal view.

The following is work todo:

- administrating parameters to rsync
- setting parameters for backup and backup catalog of changed data before synchronizing
- disable and enable default parameters to rsync

![](/images/RsyncOSX/master/swiftui/rsynccommand.png)

## Add and edit configurations

Within the `Add or edit` menu, either update data about an existing task or add new tasks. The user can change all basic data about a task. The user **cannot** change the above for snapshot tasks.

There is also function for adding profiles.

![](/images/RsyncOSX/master/swiftui/addedit.png)


## Administrate snapshots

RsyncOSX supports snapshot tasks. It is important to administrate (delete) older snapshots not needed. RsyncOSX supports a couple of plans to assist in which snapshoots to keep and which to delete.

The following is work todo:

- delete snapshots

![](/images/RsyncOSX/master/swiftui/snapshot.png)
![](/images/RsyncOSX/master/swiftui/snapshottag.png)

## Not yet implemented

The following is **not yet** implemented:

- **restore** of data
- execution of **shellout tasks**, configurations with pre and post shell scripts
- administration of parameters to rsync
- administration of snapshot tasks
- shortcut codes for various tasks
- no start or stop of the menu app for scheduling of tasks
- not yet localized, but prepared for it
