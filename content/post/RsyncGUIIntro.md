+++
author = "RsyncOSX"
date = "2020-04-01"
title =  "A short intro to RsyncGUI"
tags = ["introduction","rsyncgui"]
categories = ["general information"]
description = "RsyncGUI is the Apple Mac Store version of RsyncOSX."
lastmod = "2021-01-24"
+++
RsyncGUI is a **Sandboxed** application and if you plan to use remote servers there are some [first start info](/post/rsyncguifirststart) to read. Also read about the `--delete` parameter to rsync below. Connecting RsyncGUI to remote servers are normally through ssh. RsyncGUI need permission to read the home catalog and the `.ssh` catalog. There are more info about that in [the first start info](/post/rsyncguifirststart).

## Some words about RsyncGUI

The UI of RsyncGUI can for users who dont know rsync, be difficult or complex to understand. Using RsyncGUI requires some knowledge of `rsync`. The main objective for RsyncGUI is to ease the use of `rsync`, not teach macOS users how to use `rsync`. That is beyond the scope of RsyncGUI. Setting the wrong parameters to rsync can result in deleted data. And RsyncGUI will not stop you for doing so. That is why it is very important to execute a simulated run (`--dry-run`) and inspect what happens before a real run.


### RsyncGUI as your main tool for backup

If your plan is to use RsyncGUI as your main tool for backup of files, please investigate and understand the limits of it. RsyncGUI is quite powerful, but it is might not the primary backup tool for the average user of macOS.

### The --delete parameter

Caution about RsyncGUI and the `--delete` parameter. The parameter is a default parameter. The parameter instructs rsync to keep the source and destination synchronized (in sync). The parameter instructs rsync to delete all files in the destination which are not present in the source.

Every time you add a new task to RsyncGUI, execute an estimation run (`--dry-run`) and inspect the result before executing a real run. If you by accident set an empty catalog as source RsyncGUI (rsync) will delete all files in the destination.

### Rsync version 2.6.9

The default version of rsync in macOS is old, version 2.6.9, protocol version 29 released in nov 2006. This version of rsync does not support snapshot tasks. If you want to utilize [snapshot tasks](/post/snapshots) or [scheduling of tasks](/post/scheduletasks/) please use RsyncOSX instead.

## Where to start?

You can get up and running in just a few clicks. Open RsyncGUI and select the **Add tab**. Use the GUI to select any local and attached volumes. If not RsyncGUI will ask for permission to access these catalogs after entering.

![](/images/RsyncOSX/master/intro/main1.png)

In the Add tab, as an example, add the `/Users/thomas/Documents` catalog as source and the `/mounted_Volume/Documents` catalog as remote. This will setup a task to synchronize (backup) all content of the Documents to the attached backup volume in catalog Documents. You can also use drag and drop from Finder to add data.

Select `Add` button to add task.

Return back to the **Synchronize tab**, select the task and you are ready to go. A **double click** on the selected will execute a estimation (`--dry-run`) and present the result. The next double click will execute the real synchronizing of data.

![](/images/RsyncOSX/master/intro/main2.png)

## Type of tasks

There  are two types of how to synchronize source and destination (backup):

- **synchronize** source and backup location, any changed and deleted files in backup location will either be overwritten or deleted
  - this is the default synchronize task in RsyncGUI, after execution source and destination (backup) is 100% in sync if there are no --exclude parameters to rsync
  - an --exclude parameter instructs rsync to disregard files, catalogs and patterns included in the parameter
- **syncremote** which synchronize **a remote source** to your local Mac.
  - please pay attention before using this task, if you syncremote an empty source it will delete all local files

Snapshot tasks is not possible in RsyncGUI, see [the RsyncGUI Changelog](/post/rsyncguichangelog).

## How to execute tasks

There are several ways to execute the tasks. And it is **always** advised to execute an estimation run after adding a new task to verify it does what you expect it to do.

![](/images/RsyncOSX/master/intro/main3.png)

Tasks can be aborted at any time by selecting the stop button. For more info about the various tasks, [please see RsyncOSX docs](/post/rsyncosxdocs/). 

1. a `double click` on a task executes first an estimation run, the next double click executes the real run
2. `⌘R`shortcut for immediate execute the selected task (no estimation run)
3. `⌘B` shortcut for automatic synchronizing
4. `⌘T` shortcut for quick synchronizing
5. execute the selected tasks (one or more)

![](/images/RsyncOSX/master/intro/main4.png)

## Verify a task (--dry-run)

Before a real execution of a task, please execute an estimation run. An estimation run is started by selecting a task and the stat light is yellow. A double click on the task does a simulated run and displays which files to be transferred. Please pay attention to the info in the display when the simulate run is completed. A drop down display presents the result.
