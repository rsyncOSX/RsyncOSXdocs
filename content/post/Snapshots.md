---
layout: post
title:  "Snapshots"
permalink: Snapshots
---
Snapshot is an effective method for saving changed and deleted data. Snapshot utilize [hardlinks](https://en.wikipedia.org/wiki/Hard_link) and only changed and deleted data are saved as separate files in a snapshot. Files which are not changed are  hardlinks to the original file in the snapshot.

## Snapshot administration - delete and keep snapshots

Deleting snapshots is a **destructive** operation and should be performed with care. It is important to have a plan about which snapshots to keep and which to delete. RsyncOSX utilizes a simple plan for delete and keep snapshots. The plan is based upon three parts:

- the current week
  - keep all the snapshots within the current week
- the current month minus the current week
  - keep all snapshots for the selected Day of week, e.g all snapshots every Sunday this month
- previous months (and years)
  - keep the snapshot in the last week of month for selected Day of week, e.g the last Sunday in the month

Snapshots which does not follow plan are automatically marked for deleting. To actually delete the marked snapshots require to select the `Delete` button.

## Utilizing Snapshots

The snapshot feature enables saving changed and deleted files ahead of a new synchronizing task. The snapshot saves the current state of all files in a separate directory ahead of any changes or deletions. Changed and deleted files can then be restored utilizing the copy single files features. A restore will copy the **last** snapshot from remote storage to either the source directory or a temporary restore directory.

- snapshots works on either local attached disks and remote hosts
- standard rsync synchronize tasks cannot be converted to snapshots, creating snapshots starts with a full sync in the first snapshot catalog (`~/snapshots/data/1`)
- the snapshot feature utilizes the `--link-dest` parameter to rsync
  - use either version 3.1.2 or 3.1.3 of [rsync](https://rsync.samba.org/) if the snapshot feature will be used
  - [version 3.1.2](https://download.samba.org/pub/rsync/src/rsync-3.1.2-NEWS) of rsync fixed a bug regarding the `--link-dest` parameter
  - [version 3.1.3](https://download.samba.org/pub/rsync/src/rsync-3.1.3-NEWS) of rsync was released 28 January 2018

## How does the snapshots work?

Every snapshot is in sync with local catalog at the time of creating the snapshot. Previous versions of files can be restored from snapshots. The snapshot is by utilizing the `--link-dest` parameter to rsync. The rsync parameters for snapshots are:

`--link-dest=~/snapshots/n-1 /Volumes/.../user/data/ user@remote.server:~/snapshots/n`

where

- `n` is the number of snapshots
- and `/Volumes/.../data/` is the source catalog
- and the remote catalogs is `~/snapshots/`

If remote catalog is a local volume full path must be added. The source catalog is **never** touched, only read by rsync. RsyncOSX creates the snapshots within the remote catalog. The `~` is expanded to the user home catalog on remote server. Utilizing snapshot on local attached disks require full path for remote catalog.

- `~/snapshots/1` - snapshot 1
  - a full sync when snapshot is created
- `~/snapshots/2` - snapshot 2
  - the next snapshots saves the changed files and makes hard links for files not changed
- `~/snapshots/n` - snapshot n
  - n is the latest snapshot

When the old snapshots are deleted, the filesystem takes care of saving the real files which are hard linked.

### Create a snapshot task

To create a snapshot task select `snapshots` as type in `Add` tab.
```
Important: do not copy and paste command for execution within
a terminal window. RsyncOSX saves the number n to the
configuration. The number n is the next snapshot number.
The number n is used when computing the parameter for rsync
and is picked up from the configuration.
```
