+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Some screenshots of next version"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-03-02"
+++
The UI will change as the development continues. But the overall structure and navigation will be like the views below.

The screenshots and info are updated **2 March 2021**.

## Error handling

The error handling is better in this version. If e.g rsync produces the word `error` in the output,  an alert will inform about it. If a validate of input, when adding new configurations fails , an alert will inform about the error.

## Start

The default view when starting the app. Select a profile at any time and the app reloads the data. The start might be `Multiple tasks`. The main view informs about which version of rsync is utilized and if JSON or PLIST is used for storing configurations and schedules.

![](/images/RsyncOSX/master/swiftui/start.png)

### What is missing

- nothing special

## Multiple tasks

Choose `Estimate` and then `Execute` after estimation is completed. The estimation marks tasks with data for synchronizing. Or just go for all tasks, no estimation and execute direct. An example of how easy it is too create the UI is the [Estimation View](https://github.com/rsyncOSX/RsyncSwiftUI/blob/main/RsyncSwiftUI/Views/Multitask/EstimationView.swift). There are approx only 60 lines of code for the layout of the estimation view (below).

The view also includes a delete function for configurations.

![](/images/RsyncOSX/master/swiftui/multiple.png)

### What is missing

- nothing special
- the code is stable and fully working

## Single task

If you want more control, select `Single task`. Choose either `Estimate` and `Execute` or `Now`, which executes without estimation.

![](/images/RsyncOSX/master/swiftui/single.png)

### What is missing

- nothing special
- the code is stable and fully working

## Parameters to rsync and the command

Viewing the actual rsync command and parameters to rsync for one task. The user can (when the app is released) set any parameter to rsync. The `Copy` button copy the actual rsync command (--dry-run) to memory for possible paste it into a terminal view.

![](/images/RsyncOSX/master/swiftui/rsynccommand.png)

### What is missing

- administrating parameters to rsync
- setting parameters for backup and backup catalog of changed data before synchronizing
- disable and enable default parameters to rsync

## Add and edit configurations

Within the `Add or edit` menu, either update data about an existing task or add new tasks. The user can change all basic data about a task. The user **cannot** change the above for snapshot tasks. There is also function for adding profiles.

![](/images/RsyncOSX/master/swiftui/addedit.png)

### What is missing

- nothing special
- the code is stable and fully working

## Administrate snapshots

RsyncOSX supports snapshot tasks. It is important to administrate (delete) older snapshots not needed. RsyncOSX supports a couple of plans to assist in which snapshoots to keep and which to delete.

![](/images/RsyncOSX/master/swiftui/snapshot.png)
![](/images/RsyncOSX/master/swiftui/snapshottag.png)

### What is missing

- delete snapshots is missing

## User settings

Some user settings.

![](/images/RsyncOSX/master/swiftui/settings.png)

### What is missing

- nothing special
- the code is stable and fully working

## SSH settings

Some SSH settings.

![](/images/RsyncOSX/master/swiftui/ssh.png)

### What is missing

- nothing special
- the code is stable and fully working

## Missing main functions

The following is **not yet** implemented:

- administration (create, edit and delete) of **schedules** and **logs**
- **restore** of data
- execution of **shellout tasks**, configurations with pre and post shell scripts
- administration of parameters to rsync
- administration of snapshot tasks
- shortcut codes for various tasks
- no start or stop of the menu app for scheduling of tasks
- not yet localized, but prepared for it
