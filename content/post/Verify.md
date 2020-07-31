+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Verify and changed files"
tags = ["verify"]
categories = ["rsync"]
description = "Sometimes you want to verify the synchronized data."
lastmod = "2020-07-31"
+++
The view is depended upon selecting a row in Synchronize view. When the row is selected the numbers of source and remote destination are collected when either the `Changed` or `Verify` button is pressed.

### The archive parameter

The `--archive` parameter is the normal parameter to use in synchronize and snapshot tasks because it is fast. The `--archive` parameter to [rsync](https://en.wikipedia.org/wiki/Rsync) preserves a lot of attributes of files when synchronizing. Files transferred in --archive mode ensures that symbolic links, devices, permissions, ownerships, modification times, ACLs, and extended attributes are preserved. When synchronizing files based upon the --archive parameter, rsync compares file size and last modification time to compute which files to be synchronized.

### The checksum parameter

The `--checksum` parameters forces rsync to evaluate files based upon 128-bit [MD5](https://en.wikipedia.org/wiki/MD5) checksum. Rsync computes and compares the checksum of all files. Files with not equal checksum are listed. This is a time consuming task because rsync computes and compare the checksum for every file and it is therefore best for verifying a backup.

About the verify function
|---|
RsyncOSX does not evaluate the result from neither a verify or changed function. The user has to evaluate the result self and take required actions.

The Verify button kicks off the `--checksum` process. The output is appended and refreshed every time rsync output a new line.

The Changed button kicks of a `--dry-run` restore task. Changed and deleted files in source compared to last synchronizing or snapshot task are listed. This process is utilizing the --archive parameter. For both functions the corresponding rsync command is presented.

If the **verify** finds files not synchronized a touch command on file will update timestamp on file and next synchronize task will copy missing files.

Below is sample of a verify task. 66 files are verified as not equal.

![](/images/RsyncOSX/master/verify/verify.png)
