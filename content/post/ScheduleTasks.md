+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Scheduled task"
tags = ["scheduling","menu app"]
categories = ["synchronize"]
description = "Tasks can be scheduled for executing."
lastmod = "2020-12-13"
+++
By default the schedules part is not enabled, enable the schedule part in the userconfig. The schedules is available by a button within the main view.

The [menu app](/post/menuapp/) to RsyncOSX is responsible for executing scheduled tasks. Adding and deleting scheduled tasks are done within RsyncOSX. By selecting a row and choose schedule applies a scheduled. All schedules is set to start at selected date.

{{< image src="/images/RsyncOSX/master/schedule/schedule1.png" alt="" position="center" style="border-radius: 8px;" >}}

The menu app is reloading the schedules after each scheduled task is completed. By reloading the schedules all changes is also applied to the menu app.

There are three choices for schedules:

- `once` is executed once at date and time given
- `daily` is executed every 24-hour from a selected date
- `weekly` as for daily, but every 7 day from a selected date

The user can set multiple schedules on one task.

Select task (row), set the start date and time and select the schedule (once, daily or weekly) to set up a schedule. The schedule is a stack of tasks. The top most element is the first task to be executed. RsyncOSX keeps track of the first task only. All other scheduled tasks remains on stack until popped of.

The stack is a reference only to a configuration (by a hidden key). The user can change anything regarding a configuration up to the moment the task is executed by schedule. If a configuration is deleted all scheduled tasks connected to configuration is deleted as well.

The [menu app](/post/menuapp/) should be started from RsyncOSX by either `⌘S` shortcut or from the File menu.

The yellow flag in column Sched indicates there are active scheduled tasks. The flag is either yellow or green. Green is next task within one hour.

{{< image src="/images/RsyncOSX/master/schedule/schedule2.png" alt="" position="center" style="border-radius: 8px;" >}}
