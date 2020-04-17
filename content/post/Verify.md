---
layout: post
title:  "Verify and changed files"
permalink: Verify
---
The view is depended upon selecting a row in Synchronize view. When the row is selected the numbers of source and remote destination are automatically collected.

The `--archive` parameter is the normal parameter to use in synchronize and snapshot tasks because it is fast. The `--archive` parameter to [rsync](https://en.wikipedia.org/wiki/Rsync) preserves a lot of attributes of files when synchronizing. Files transferred in `--archive` mode ensures that symbolic links, devices, permissions, ownerships, modification times, ACLs, and extended attributes are preserved. When synchronizing files based upon the `--archive` parameter, rsync compares file size and last modification time to compute which files to be synchronized.

The `--checksum` parameters forces rsync to evaluate files based upon 128-bit [MD5](https://en.wikipedia.org/wiki/MD5) checksum. Rsync computes and compares the checksum of all files. Files with not equal checksum are listed. This is a more time consuming task because rsync computes and compare the checksum for **every** file and it is therefore best for verifying a backup.
```
Warning: RsyncOSX does not evaluate the result from neither
a verify or changed function. The user has to evaluate the
result self and take required actions.
```
The `Verify` button kicks off the `--checksum` process. The output is appended and refreshed every time rsync output a new line.

The `Changed` button kicks of a `--dry-run` restore task. Changed and deleted files in source compared to last synchronizing or snapshot task are listed. This process is utilizing the `--archive` parameter. For both functions the corresponding rsync command is presented.

If the **verify** finds files not synchronized a `touch` command on file will update timestamp on file and next synchronize task will copy missing files.

Below is sample of verify for **standard** synchronizing task. Seven files are verified as not equal. The seven files are also identified by the normal backup task.

![](/images/RsyncOSX/master/verify/verify.png)

Below is sample of verify for **snapshot** synchronizing task. The source and backup is identical after the synchronizing task.

![](/images/RsyncOSX/master/verify/snapshot.png)

A verify is probably best to to do after a synchronizing is completed. If there are any files which checksums are not equal, rsync list those files. In the view above all checksums are equal and backup is verified equal to source.

For snapshot tasks the synchronize and verify rsync command is slightly different.

![](/images/RsyncOSX/master/verify/snapshot2.png)
![](/images/RsyncOSX/master/verify/snapshot3.png)
