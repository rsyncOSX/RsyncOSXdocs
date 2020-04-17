---
layout: post
title:  "A short intro to RsyncOSX"
permalink: Intro
---
All configurations to execute are listed in table. From the Synchronize view most actions (edit configurations, adding parameters to rsync, delete configurations) regarding configurations are executed. Configurations can be saved in user selected profiles. The profile in use is shown in label `Profile: profilname`. Information about new or delete files and numbers remote of directories are only available if version 3.x of rsync is used.

### Passwordless logins to remote servers

Using RsyncOSX for backup to **remote servers** [require to setup ssh passwordless logins](/Remotelogins). The intro is not depended on setting up remote servers.

## Where to start?

You can get up and running in just a few clicks. Open RsyncOSX and select the `Add` tab.
![](/images/RsyncOSX/master/intro/main1.png)
In the `Add` tab, as an example, add the Documents catalog as source and the `/Volumes/backup/Documents` catalog as remote. This will setup a task to synchronize (backup) all content of the Documents to the attached `backup` volume in catalog `Documents`. Use drag and drop from Finder to add data.

Select `Add` button to add task.
![](/images/RsyncOSX/master/intro/main2.png)
![](/images/RsyncOSX/master/intro/main3.png)
Go back to the `Synchronize` tab, select the task and you are ready to go.
![](/images/RsyncOSX/master/intro/main4.png)

## Four type of tasks

There are **four** types of how to synchronize source and destination (backup):

(1) **synchronize** source and backup location, any changed and deleted files in backup location will either be overwritten or deleted
  - this is the standard synchronize task in RsyncOSX, after execution source and destination (backup) is 100% in sync if there are no `--exclude` parameters to rsync
  - an `--exclude` parameter instructs rsync to disregard files, catalogs and patterns included in the parameter

(2) **snapshot**  tasks, a [snapshot](/Snapshots) of previous synchronize task is stored before a new task is executed, number of snapshots are user defined, copy deleted or previous versions of files from snapshots

(3) **synchronize** and **save changed** and **deleted** files in a separate backup catalog by adding a [parameters](/Parameters) to rsync

(4) **syncremote** task, this is a kind of restore task, syncing data from a **remote server** to local disk on Mac

## How to execute any type of tasks

All tasks can be **aborted** at any time by selecting the stop button.

![](/images/RsyncOSX/master/intro/menu1.png)

First select **one** task in Synchronize view, applies to (1) and (2) below.

(1) single task, a **double click** on a task executes first a test run (`--dry-run`), the next double click executes the real run

(2) **`⌘R`** (execute one task now) - shortcut for immediate execute the selected task
- if a task is executed by shortcut `⌘R`, a select of another task during execution will terminate (abort) the current task

(3) **`⌘B`** (execute all tasks now) - shortcut for **automatic executing** backups or by select the double arrow, the command checks tasks for files to be synchronized and automatically executes those tasks

![](/images/RsyncOSX/master/intro/menu4.png)

(4) **quick backup**, select the marked arrow button in menu bar

![](/images/RsyncOSX/master/intro/menu2.png)

- start with dynamic view of local vs remote storage, automatically selecting tasks with files to be synchronized

(5) **schedule** a task, scheduled tasks are executed according to date and time, either once, daily or weekly

## YouTube videos

There are a couple of short YouTube videos of RsyncOSX:

- [getting](https://youtu.be/MrT8NzdF9dE) RsyncOSX and installing it
  - the video also shows how to create the two local ssh certificates for password less logins to remote server
- adding and executing the [first backup](https://youtu.be/8oe1lKgiDx8)
