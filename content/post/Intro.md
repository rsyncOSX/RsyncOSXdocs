+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "A short intro to RsyncOSX"
tags = ["introduction"]
categories = ["general information"]
description = "How to get started with RsyncOSX."
+++
All configurations to execute are listed in table. From the Synchronize view most actions (edit configurations, adding parameters to rsync, delete configurations) regarding configurations are executed. Configurations can be saved in user selected profiles. The profile in use is shown in label `Profile: profilname`. Information about new or delete files and numbers remote of directories are only available if version 3.x of rsync is used.

## Passwordless logins to remote servers

Using RsyncOSX for backup to **remote servers** [require to setup ssh passwordless logins](/post/remotelogins/). The intro is not depended on setting up remote servers.

## Where to start?

You can get up and running in just a few clicks. Open RsyncOSX and select the Add tab.

![](/images/RsyncOSX/master/intro/main1.png)

In the Add tab, as an example, add the `/Users/thomas/Documents` catalog as source and the `/Volumes/backup/Documents` catalog as remote. This will setup a task to synchronize (backup) all content of the Documents to the attached backup volume in catalog Documents. Use drag and drop from Finder to add data.

Select Add button to add task.

![](/images/RsyncOSX/master/intro/main2.png)
![](/images/RsyncOSX/master/intro/main3.png)

Go back to the Synchronize tab, select the task and you are ready to go.

![](/images/RsyncOSX/master/intro/main4.png)

A double click on the row executes a estimation run. Another double click executes the real run.

## Four type of tasks

There are **four** types of how to synchronize source and destination (backup):

(1) synchronize source and backup location, any changed and deleted files in backup location will either be overwritten or deleted
- this is the default synchronize task in RsyncOSX, after execution source and destination (backup) is 100% in sync if there are no --exclude parameters to rsync
- an --exclude parameter instructs rsync to disregard files, catalogs and patterns included in the parameter

(2) snapshot  tasks, [a snapshot](/post/Snapshots) of previous synchronize task is stored before a new task is executed, number of snapshots are user defined, copy deleted or previous versions of files from snapshots

(3) synchronize and save changed and deleted files in a separate backup catalog by [adding user parameters](/post/userparameters/) to rsync

(4) syncremote task, this is a kind of restore task, syncing data from a remote server to local disk on Mac
- please pay attention before using this task, if you syncremote an empty source it will delete all local files

## How to execute any type of tasks

![](/images/RsyncOSX/master/intro/menu1.png)

Tasks can be aborted at any time by selecting the stop button.

1. a `double click` on a task executes first a test run, the next double click executes the real run
2. `⌘R`shortcut for immediate execute the selected task (no test run)

![](/images/RsyncOSX/master/intro/menu4.png)

3. `⌘B` shortcut for automatic synchronizing

![](/images/RsyncOSX/master/intro/menu2.png)

4. `⌘T` shortcut for quick synchronizing

![](/images/RsyncOSX/master/intro/menu3.png)

5. execute the selected tasks (one or more)

## YouTube videos

There are two short YouTube videos of RsyncOSX:

- [how to get and install RsyncOSX](https://youtu.be/d-srHjL2F-0)
- [adding and executing the first backup](https://youtu.be/vS5_rXdTtZ8)
