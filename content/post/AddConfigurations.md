+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Add configurations"
description = "How to enter synchronize tasks into RsyncOSX."
tags = ["add configurations"]
categories = ["configurations"]
lastmod = "2020-07-16"
+++
Adding a configuration is easy. A configuration require minimum a **local catalog** and a **remote catalog**. After entering information about a configuration select the Add button to add it to RsyncOSX. Continue adding new configurations until completed and configurations are saved to permanent storage after each entry.

Select local catalog either by drag and drop or by enter text directly. For remote catalogs only drag and drop for local attached volumes. For remote server catalogs enter by text only.

There are four types of tasks
- synchronize, which is default and keeps source and destination in sync
- snapshots, save changes and deletes ahead of a synchronize
- syncremote, remote is source, synchronize a remote source to a local volume
- single file

## Sample configuration

Local catalog and Remote catalog are added either by using drag and drop from filemanager or by text only. If enter by text please remember to add the full path. Remote catalogs is entered either by full paths or use the ~ character to expand remote user home catalog.

The Capacity button query remote storage in all configurations about available storage space. Only valid for remote hosts.

![](/images/RsyncOSX/master/add/add.png)
### Catalog parameters
- **Local catalog**: required field `/Users/thomas/Documents/` my Documents catalog in my home catalog
- **Remote catalog**: required field `~/Documents/`
  - the backup catalog for user thomas. The ~ is expanded as the home catalog with full path by the remote operating system. The remote catalog might also be added by full path, depends where the backup catalog is placed on remote server
  - the backup catalog might also be a local catalog on a local attached disk
- **Dont´t add trailing**: `/`, by default a trailing `/` is added to both source and destination
### Remote server parameters
- **Remote username**: `thomas` username for login to remote server
- **Remote server**: `10.0.0.57` either server name or IP-address for remote server
- **ID**: `My docs catalog` informal tag for the configuration
### Task
- **Type**: there are four types of tasks, `synchronize` which is default, `snapshots`, `syncremote` and `single file`.
### Optional pre and post task
- **pretask**: attach optional pre shell script to the synchronize command. The `pre.sh`is executed ahead of the synchronize command, the `post.sh` after the synchronize command. The scripts are normal shell scripts as if executed from the command line.
  - switch execute shell script on/off
- **posttask**: attach optional post shell script to the synchronize command. The `post.sh` is executed after the synchronize command.
  - switch execute shell script on/off
- **Halt on error**: if the phrase "error" occurs in the output from the `pre.sh` command, if `on` the execution of synchronize command is aborted

Select the Add button when completed and configuration is added to RsyncOSX. RsyncOSX adds a trailing / character to both local and remote volume. After selecting the Add button another configuration might be added. Any changes (edit or delete) to configurations are done from the Synchronize view. Additional parameters to rsync might be added utilizing the Parameter button.
