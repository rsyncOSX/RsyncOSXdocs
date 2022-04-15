+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Add tasks"
description = "How to enter synchronize tasks into RsyncOSX."
tags = ["add tasks"]
categories = ["tasks"]
lastmod = "2020-12-13"
+++
A task require minimum a **local catalog** and a **remote catalog**. After entering information about a task select the `Add` button to add it to RsyncOSX. Continue adding new tasks until completed and tasks are saved to permanent storage after each entry. Select local catalog either by GUI, drag and drop or by enter text directly.

Add is selected by choosing the green plus sign in top main menu.

{{< image src="/images/RsyncOSX/master/add/addmain.png" alt="" position="center" style="border-radius: 8px;" >}}

For remote catalogs only drag and drop for local attached volumes. For remote server catalogs enter by text only.

{{< image src="/images/RsyncOSX/master/add/add.png" alt="" position="center" style="border-radius: 8px;" >}}

### Catalog parameters
- **Task**
  - synchronize, which is default and keeps source and destination in sync
  - [snapshots](/post/snapshots/), save changes and deletes ahead of a synchronize
  - syncremote, remote is source, synchronize a remote source to a local volume

- **Local catalog**:
  - required field
- **Remote catalog**:
  - required field
  - the backup catalog might also be a local catalog on a local attached disk

- **ID**:
  - informal tag for the task

- **Dont´t add trailing**: `/`
  - by default a trailing `/` is added to both source and destination

### Remote server parameters
- **Remote username**:
  - username for login to remote server
- **Remote server**:
  - either server name or IP-address for remote server

### Shell scripts

The shell scripts names and locations is selected by the user.

- **pretask**: attach optional pre shell script to the synchronize command, the shell script is executed **ahead** of the synchronize command
  - switch execute shell script on/off
- **posttask**: attach optional post shell script to the synchronize command, the shell script is executed **after** the synchronize command
  - switch execute shell script on/off
- **Halt on error**: if the phrase "error" occurs in the output from the `pre.sh` command, if `on` the execution of synchronize command is aborted

## Add tasks

Select the `Add` button when completed and task is added to RsyncOSX. RsyncOSX adds a trailing / character to both local and remote volume. After selecting the Add button another task might be added.

Any changes to a task (edit or delete) are done from the Synchronize view.

## Local and Remote buttons

The main objective for the assist function is to ease adding tasks. Assist picks up the following:

- the name of all catalogs within your home directory
- the path of your home directory
- and if there are added tasks, remote server and remote user from the current profile

Selecting `Local` or `Remote` transfer the data to the add new task. The following is transferred from the selected dropdown values to the add view when selecting either `Local` or `Remote`:

- Local catalog (in Add view): `Local home`  + `/` + `Catalogs`
- Remote catalog (in Add view): `~`  + `/` + `Catalogs`
- Remote username (in Add view): `Remote users`
- Remote server (in Add view): `Remote computers`
