+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Restore files"
tags = ["restore"]
categories = ["synchronize"]
description = "How to restore files, there are two options."
+++
A restore should always be executed carefully. There is always a possibilty to delete or replace newer files with older when executing a restore. It is advised to always do a restore to a temporary catalog and review the restored files. There are two types of restore:

- full restore
  - if the remote (destination) is a snapshot the Full restore is from the latest snapshot
- restore files
  - if the remote (destination) is a snapshot the file list might be huge, depends upon how many snapshots and how many files in a snapshot
  - any file from any snapshot might be restored

**Step one** in a restore is to select from which configuration a restore is to be executed.

### Temporary restore path

Only a full restore is allowed from remote catalog to source catalog. Default restore for full restore and restore files are to a temporary restore path. To set a temporary restore path [select userconfiguration](/post/userconfiguration/) and set `temporary path restore`.

To do a restore, either full or by file, an estimation is normally required. The status light changes from red to yellow when an estimation can be executed. The status light is green when a restore can be executed.

You can restore single file or catalogs by a double click in the right table, if restore by files are selected and RsyncOSX has retrieved file list from remote location.

### Full restore

A full restore might be restored to the original source catalog on the Mac. It is not advised to do so. Always execute a restore to the temporary restore path.

![](/images/RsyncOSX/master/restore/restore.png)

The button `Do the real thing:` must be checked before a restore can be executed (after an estimation run). If not only a simulation message is shown.

### Restore files

Restore of files and catalogs is only allowed to a `temporary path restore`.

To restore files or catalogs select the restore by file button. RsyncOSX retrieves files from remote location. Select either a file or catalog, execute an `Estimate` and then a `Restore`. A double click on a file or catalog in right table will execute a restore right away.

![](/images/RsyncOSX/master/restore/restore2.png)
