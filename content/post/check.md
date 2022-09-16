+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Verify synchronized files"
tags = ["verify","checksum","check"]
categories = ["synchronize"]
lastmod = "2020-12-13"
+++
The verify of synchronized data is triggered by the `File -> Check synchronized` menu or the `⌘K` shortcut. The `--archive` parameter is the normal parameter to use in synchronize and snapshot tasks because it is fast. The `--archive` parameter to [rsync](https://en.wikipedia.org/wiki/Rsync) preserves a lot of attributes of files when synchronizing. Files transferred in --archive mode ensures that symbolic links, devices, permissions, ownerships, modification times, ACLs, and extended attributes are preserved. When synchronizing files based upon the --archive parameter, rsync compares file size and last modification time to compute which files to be synchronized.

## The checksum parameter

The `--checksum` parameters forces rsync to evaluate files based upon 128-bit [MD5](https://en.wikipedia.org/wiki/MD5) checksum. Rsync computes and compares the checksum of all files. Files with not equal checksum are listed. This is a time consuming task because rsync computes and compare the checksum for every file and it is therefore best for verifying a backup. RsyncOSX does not evaluate the result from the check function. The user has to evaluate the result self and take required actions.

The `⌘K` shortcut kicks off the `--checksum` process. The output is appended and refreshed every time rsync output a new line.

If the **check** finds files not synchronized a touch command on file will update timestamp on file and next synchronize task will copy missing files.
