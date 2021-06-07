+++
author = "Thomas Evensen"
date = "2020-04-16"
title =  "Add configurations"
description = "How to enter synchronize tasks into RsyncOSX."
tags = ["add configurations"]
categories = ["configurations"]
lastmod = "2020-12-13"
+++
A configuration require minimum a **local catalog** and a **remote catalog**. After entering information about a configuration select the `Add` button to add it to RsyncOSX. Continue adding new configurations until completed and configurations are saved to permanent storage after each entry. Select local catalog either by drag and drop or by enter text directly. For remote catalogs only drag and drop for local attached volumes. For remote server catalogs enter by text only.

There is also an [Assist function](/post/addconfigurations/#assist) which picks up your local catalogs. You can also add your remote info for easy to add new tasks.

![](/images/RsyncOSX/master/add/add.png)

### Catalog parameters
- **Local catalog**: required field
- **Remote catalog**: required field
  - the backup catalog might also be a local catalog on a local attached disk


### Remote parameters
- **Remote username**:
  - username for login to remote server
- **Remote server**:
  - either server name or IP-address for remote server
- **ID**:
  - informal tag for the configuration

### Task
- synchronize, which is default and keeps source and destination in sync
- [snapshots](/post/snapshots/), save changes and deletes ahead of a synchronize
- syncremote, remote is source, synchronize a remote source to a local volume
- **Dont´t add**: `/`
  - by default a trailing `/` is added to both source and destination


### Shell scripts

The shell scripts names and locations is selected by the user.

- **pretask**: attach optional pre shell script to the synchronize command, the shell script is executed **ahead** of the synchronize command
  - switch execute shell script on/off
- **posttask**: attach optional post shell script to the synchronize command, the shell script is executed **after** the synchronize command
  - switch execute shell script on/off
- **Halt on error**: if the phrase "error" occurs in the output from the `pre.sh` command, if `on` the execution of synchronize command is aborted

## Add configurations

Select the `Add` button when completed and configuration is added to RsyncOSX. RsyncOSX adds a trailing / character to both local and remote volume. After selecting the Add button another configuration might be added. Any changes (edit or delete) to configurations are done from the Synchronize view. Additional parameters to rsync might be added utilizing the Parameter button.

## Assist

The main objective for the assist function is to ease adding configurations. Assist picks up the following:

- the name of all catalogs within your home directory
- the path of your home directory
- and if there is added tasks, remote server and remote user from the current profile

There is not possible to save, change or delete values in assist.

Selecting `Local` or `Remote` transfer the data to the add new configrations screen. The following is transferred from the selected dropdown values to the add view when selecting either `Local` or `Remote`:

- Local catalog (in Add view): `Local home`  + `/` + `Catalogs`
- Remote catalog (in Add view): `~`  + `/` + `Catalogs`
- Remote username (in Add view): `Remote users`
- Remote server (in Add view): `Remote computers`

![](/images/RsyncOSX/master/add/assist.png)

- `Local home`: your home catalog
- `Catalogs`: catalogs to synchronize, the catalog is added to `Local home` and `Remote home`.
- `Remote users`: remote username if `Remote computers` are used.
- `Remote computers`: name or IP-adress of remote computer
