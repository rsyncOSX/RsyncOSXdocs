---
layout: post
title:  "Restore files"
permalink: Restore
---
There are two types of restore files:
- Full restore
  - if the remote (destination) is a snapshot the Full restore is from the latest snapshot
- Restore files
  - if the remote (destination) is a snapshot the file list might be huge, depends upon how many snapshots and how many files in a snapshot
  - any file from any snapshot might be restored

Only full restore is allowed from remote (destination) catalog to source catalog. But the default restore for both Full restore and Restore files are to a temporary catalog.
![](/images/RsyncOSX/master/restore/restore.png)
To do a restore, either full or files, an estimation is required. The status light changes from red to yellow when an estimation can be executed. The status light is green when a restore can be executed.

The button `Do the real thing:` must be checked before a restore is executed. If not only a simulation message is shown.
![](/images/RsyncOSX/master/restore/restore2.png)
