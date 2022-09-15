+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Execute single tasks"
tags = ["single task","edit tasks"]
categories = ["synchronize"]
description = "Execute single task, first a verify run and then the real run."
lastmod = "2020-12-13"
+++
In Synchronize view tasks can be executed as single tasks. Execute single tasks require two **double clicks**:

- the first double click for **estimation** and
- the second double click for **executing** the task

The output from rsync is presented after each run.

{{< image src="/images/RsyncOSX/master/synchronize/synchronize.png" alt="" position="center" style="border-radius: 8px;" >}}

## Verify and execute a single task

Execute a single task is a **two step** operation. The first is an estimation or verify run, a `dry-run` execution. The second one is the real run. A drop down view of the output from rsync is automatically presented after both steps.

A single task is executed by a double click on the selected task. Another double click executes the real run and a progress bar is presented.

If Abort is pressed execution is aborted. It is also possible [to execute several tasks](/post/severaltasks/) in one go.

## Slide left and right

Using either two fingers on the touchpad or a finger on the mouse, slide to the left will execute a single task. If the task is estimated a progress bar will pop up.

{{< image src="/images/RsyncOSX/master/singletask/executeleft.png" alt="" position="center" style="border-radius: 8px;" >}}

Sliding to the right will delete a record. Every delete must be confirmed before delete.

{{< image src="/images/RsyncOSX/master/singletask/deleteright.png" alt="" position="center" style="border-radius: 8px;" >}}

## Shell scripts

If the `Shell` column is on, it indicates there is attached shell scripts to the task, also see more info about shell scripts in the [add configuration](/post/addconfigurations/).

## Edit and params

The edit enables changing the basic info about the task. The user can add, edit, enable and disable executing shell commands to the synchronize task.

{{< image src="/images/RsyncOSX/master/singletask/edit.png" alt="" position="center" style="border-radius: 8px;" >}}

The params enables access to add and change parameters to rsync. See more info about [default parameters](/post/rsyncparameters) and [user selected parameters](/post/userparameters/).

{{< image src="/images/RsyncOSX/master/userparameters/userparameters.png" alt="" position="center" style="border-radius: 8px;" >}}

## View output

Selecting the output icon upper left corner in main view presents a view of either output from rsync or the logfile. You can switch the view by the toggle switch in left bottom. The `Copy` button copies to macOS clipboard and the `New` button creates a new logfile.

{{< image src="/images/RsyncOSX/master/singletask/rsyncoutput.png" alt="" position="center" style="border-radius: 8px;" >}}
{{< image src="/images/RsyncOSX/master/singletask/logfile.png" alt="" position="center" style="border-radius: 8px;" >}}
