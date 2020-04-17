---
layout: post
title:  "Scheduled task"
permalink: ScheduleTasks
---
The [menu app](/Menuapp) to RsyncOSX is responsible for **executing scheduled tasks**. Adding and deleting scheduled tasks are done within RsyncOSX. By selecting a row and choose schedule applies a scheduled. All schedules is set to start at selected date.

The menu app is reloading the schedules after each scheduled task is completed. By reloading the schedules all changes is also applied to the menu app.

There are three choices for schedules:

- `once`
	- is executed _once_ at date and time given
- `daily`
	- is executed _every 24-hour_ from a selected date
- `weekly`
	- as for daily, but _every 7 day_ from a selected date

Select task (row), set the start date and time and select the schedule (once, daily or weekly) to set up a schedule. The schedule is a stack of tasks. The top most element is the first task to be executed. RsyncOSX keeps track of the first task only. All other scheduled tasks remains on stack until popped of.

The stack is a reference only to a configuration (by a hidden key). The user can change anything regarding a configuration up to the moment the task is executed by schedule. If a configuration is deleted all scheduled tasks connected to configuration is deleted as well.

The [menu app](/Menuapp) should be started from RsyncOSX.

The yellow flag in column `Sched` indicates there are active scheduled tasks. The flag is either yellow or green. Green is next task within one hour.
