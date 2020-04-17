---
layout: post
title:  "A short intro to RsyncGUI"
permalink: RsyncGUIIntro
---
Please see caution about using RsyncGUI and the `--delete` parameter to rsync at bottom of this page. There is also [a first start intro](/RsyncGUIfirststart) about RsyncGUI.

### Some words about RsyncGUI

RsyncGUI is **not developed to be an easy synchronize and backup tool**. The main purpose is to ease the use of `rsync` and synchronize files on your Mac to remote FreeBSD and Linux servers. And of course restore files from remote servers. The UI might also be difficult to understand or complex if you don't know what `rsync` is. It is not required to know `rsync` but it will ease the use and understanding of RsyncGUI. But it is though, possible to use RsyncGUI by just adding a source and remote backup catalog using default parameters.

If your plan is to use RsyncGUI as your main tool for backup of files, please investigate and understand the limits of it. RsyncGUI is quite powerful, but it is might not the primary backup tool for the average user of macOS.

## When you start RsyncGUI for the first time

RsyncGUI is a sandboxed macOS app and the first to do is to grant RsyncGUI permission to read the users home catalog. When RsyncGUI is started for the first time, it asks for permission to access your home catalog. Please see the [start RsyncGUI for the first time](/RsyncGUIfirststart).

## Where to start?

You can get up and running in just a few clicks. Open RsyncGUI and select the `Add` tab. Use the GUI to select any local and attached volumes. If not RsyncGUI will ask for permission to access these catalogs after entering.
![](/images/RsyncOSX/master/intro/main1.png)
In the `Add` tab, as an example, add the Documents catalog as source and the `/Volumes/backup/Documents` catalog as remote. This will setup a task to synchronize (backup) all content of the Documents to the attached `backup` volume in catalog `Documents`. Use drag and drop from Finder to add data.

Select `Add` button to add task.
![](/images/RsyncOSX/master/intro/main2.png)
![](/images/RsyncOSX/master/intro/main3.png)
Go back to the `Execute` tab, select the task and you are ready to go.
![](/images/RsyncOSX/master/intro/main4.png)

## Type of tasks

There  are **three** types of how to synchronize source and destination (backup):

(1) **synchronize** source and backup location, any changed and deleted files in backup location will either be overwritten or deleted
  - this is the standard synchronize task in RsyncGUI, after execution source and destination (backup) is 100% in sync if there are no `--exclude` parameters to rsync
  - an `--exclude` parameter instructs rsync to disregard files, catalogs and patterns included in the parameter

(2) **syncremote** which synchronize a **remote** source to your local Mac.
  - please pay attention before using this task, if you syncremote an empty source it will delete all local files

(3) **synchronize** and **save changed** and **deleted** files in a separate backup catalog by adding a [parameters](/Parameters) to rsync

Snapshot tasks is not possible in RsyncGUI, see [the RsyncGUI Changelog](/RsyncGUIChangelog).

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

(5) mark backup tasks for **batch**, select the marked arrow button in menu bar

![](/images/RsyncOSX/master/intro/menu3.png)

- tasks which are marked for batch are selected

## Caution about RsyncGUI

Before a real execution of a task please execute an estimation run. An estimation run is started by selecting a task and the stat light is yellow. A double click on the task does a simulated run and displays which files to be transferred. Please pay attention to the info in the display when the simulate run is completed. A drop down display presents the result.

Ready for an estimation run. A double click on row executes the estimation run.
![](/images/RsyncOSX/master/intro/simulate.png)
Estimation run completed, dropdown presents result.
![](/images/RsyncOSX/master/intro/display.png)
Ready for real run. A double click on row actually executes the task.
![](/images/RsyncOSX/master/intro/realrun.png)

## The --delete parameter
```
Caution about RsyncOSX and the `--delete` parameter. The
`--delete` is a default parameter. The parameter instructs
rsync to keep the source and destination synchronized (in sync).
The parameter instructs rsync to delete all files in the
destination which are not present in the source.

Every time you add a new task to RsyncOSX, execute an estimation
run (--dry-run) and inspect the result before executing a real
run. If you by accident set an empty catalog as source
RsyncOSX (rsync) will delete all files in the destination.
```
