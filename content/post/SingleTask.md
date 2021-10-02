+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Execute single tasks"
tags = ["single task","edit tasks", "user rsync parameters"]
categories = ["synchronize"]
description = "Execute single task, first a verify run and then the real run."
lastmod = "2020-12-13"
+++
In Synchronize view (which is the opening view) tasks can be executed as singletasks. Execute single tasks requires a couple of double clicks: one for **estimation** run and the second for **executing** the real task. The output from rsync is presented after each run.

{{< image src="/images/RsyncOSX/master/synchronize/synchronize.png" alt="" position="center" style="border-radius: 8px;" >}}

The `Shell` column is on, it indicates there is attached shell scripts to the task, also see more info about shell scripts in the [add configuration](/post/addconfigurations/).

## Execute single task

Execute single tasks is a **two step** operation, one for estimation (dry-run) and one for the real task. A drop down view is automatically presented after both tasks. A single task is executed by  a double click on the selected task/row. There are five numbers in bottom page. Only version 3.x counts the number of remote directories. The numbers are files to be transferred and remote numbers. Another double click executes the real run and a progress bar is presented.

If Abort is pressed any executing task is aborted.

## Slide left and right

Using either two fingers on the touchpad or a finger on the mouse, slide to the left will execute a single task. If the task is estimated a progressbar will pop up.

{{< image src="/images/RsyncOSX/master/singletask/executeleft.png" alt="" position="center" style="border-radius: 8px;" >}}

Sliding to the right will delete a record. Every delete must be confirmed before delete.

{{< image src="/images/RsyncOSX/master/singletask/deleteright.png" alt="" position="center" style="border-radius: 8px;" >}}


## Edit and params

The edit enables changing the basic info about the task. The user can add, edit, enable and disable executing shell commands to the synchronize task.

{{< image src="/images/RsyncOSX/master/singletask/edit.png" alt="" position="center" style="border-radius: 8px;" >}}

The params enables access to add and change parameters to rsync. See more info about [default parameters](/post/rsyncparameters) and [user selected parameters](/post/userparameters/).

{{< image src="/images/RsyncOSX/master/userparameters/userparameters.png" alt="" position="center" style="border-radius: 8px;" >}}

## View output

Selecting the output icon upper left corner in main view presents a view of either output from rsync or the logfile. You can switch the view by the toggle switch in left bottom. The `Copy` button copies to macOS clipboard and the `New` button creates a new logfile.

{{< image src="/images/RsyncOSX/master/singletask/rsyncoutput.png" alt="" position="center" style="border-radius: 8px;" >}}
{{< image src="/images/RsyncOSX/master/singletask/logfile.png" alt="" position="center" style="border-radius: 8px;" >}}
