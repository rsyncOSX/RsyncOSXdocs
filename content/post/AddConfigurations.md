---
layout: post
title:  "Add configurations"
permalink: AddConfigurations
---
Adding a configuration is easy. A configuration require minimum a **Local catalog** and a **Remote catalog**. After entering information about a configuration select the Add button to add it to RsyncOSX. Continue adding new configurations until completed and configurations are saved to permanent storage after each entry.

Select **Local catalog** either by *drag and drop* or by *enter text* directly. For **Remote catalogs** only drag and drop for local volumes. For remote server catalogs enter by text only.

There are four types of tasks, `synchronize` which is standard, `snapshots`, `syncremote` and `single file`. For [snapshots](/Snapshots) see documentation.

### Sample configuration

Local catalog and Remote catalog are added either by using *drag and drop* from filemanager or *by text* only. If enter by text please remember to add the full path. Remote catalogs is entered either by full paths or use the `~` character to expand remote user home catalog. See sample configuration.

The `Capacity` button query remote storage in all configurations about available storage space. Only valid for remote hosts.
![](/images/RsyncOSX/master/add/add.png)
![](/images/RsyncOSX/master/add/add2.png)
- **Local catalog**: `/Users/thomas/Documents/`
  - my Documents catalog in my home catalog
  - required field
- **Remote catalog**: `~/Documents/`
  - the backup catalog for user thomas. The `~` is expanded as the home catalog with full path by the remote operating system. The remote catalog might also be added by full path, depends where the backup catalog is placed on remote server
  - the backup catalog might also be a local catalog on a local attached disk
  - required field
- **Remote username**: `thomas`
  - username for login to remote server
- **Remote server**: `10.0.0.57`
  - either server name or IP-address for remote server
- **ID**:
    - informal tag for the configuration
- **ssh port**:
  - if ssh communicates through other than standard port it must be set here, port 22 is default port for ssh and not require to set
- **Type**:
    - There are four types of tasks, `synchronize` which is standard, `snapshots`, `syncremote` and `single file`.
- **rsync daemon**:
    Enabling rsync daemon puts a double colon `::` in address parameter to rsync. It forces rsync to use the rsync daemon remote. There are [two possible setup for using the rsync daemon](/Rsyncdaemon). Utilizing a rsync daemon setup does **not** encrypt the transfer between client and server. To encrypt the transfer require tunneling traffic in a ssh protocol. [See how to setup ssh passwordless logins](/Remotelogins).

Select the `Add` button when completed and configuration is added to RsyncOSX. RsyncOSX adds a trailing `/` character to both local and remote volume. After selecting the Add button another configuration might be added. Any changes (edit or delete) to configurations are done from the Synchronize view. Additional parameters to rsync might be added utilizing the `Parameter` button.
