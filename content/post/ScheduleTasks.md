+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Scheduled task"
tags = ["schedules","menu app"]
categories = ["synchronize"]
lastmod = "2020-12-13"
+++
By default the schedules part is not enabled, **enable** it in the [userconfig](/post/userconfiguration/). The view for adding and delete schedules is from the schedules button from the main view.

{{< image src="/images/RsyncOSX/master/schedule/schedulesmain.png" alt="" position="center" style="border-radius: 8px;" >}}

- adding and deleting schedules within RsyncOSX
- executing scheduled tasks by the [menu app](/post/menuapp/) (shortcut `⌘S`)

{{< image src="/images/RsyncOSX/master/schedule/schedulesapp.png" alt="" position="center" style="border-radius: 8px;" >}}

There are three types of schedules:

- `once` is executed once at date and time given
- `daily` is executed every 24-hour from a selected date
- `weekly` as for daily, but every 7 day from a selected date

The user can set multiple schedules on one task.

Select task (row), set the start date and time and select the schedule (once, daily or weekly) to set up a schedule. The schedule is a stack of tasks. The top most element is the first task to be executed. RsyncOSX keeps track of the first task only. Scheduled tasks remain unactive until they are popped of the stack.

The stack is a reference only to a configuration (by a hidden key). The user can change anything regarding a configuration up to the moment the task is executed by schedule. If a configuration is deleted all scheduled tasks connected to configuration is deleted as well.

The yellow flag in column Sched indicates there are active scheduled tasks. The flag is either yellow or green. Green is next task within one hour.

{{< image src="/images/RsyncOSX/master/schedule/schedules.png" alt="" position="center" style="border-radius: 8px;" >}}
