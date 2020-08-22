+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2020-07-26"
+++
RsyncOSX is released in [version 6.4.2 (22 August 2020)](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.4.2). It is not required to install the menu app (RsyncOSXsched.app). The menu app is for executing [scheduled tasks](/post/scheduletasks) only. RsyncOSX is [signed and notarized](/post/notarized/).

## Install

The command

`shasum ~/pathtodownload/RsyncOSX-version.dmg`

will print the shasum for the .dmg file. For your own safety verify the shasums.

`RsyncOSX 6.4.2.dmg: a7c7ca525b7e34647547f353dea904d75dc4bfdc`  
`RsyncOSXsched 6.4.2.dmg: 7032b8d1e77c71df4fdc2ad8432d9ba650d6e091`

To install RsyncOSX open the downloaded RsyncOSX-version.dmg file. Drag the RsyncOSX icon to the default `/Application` catalog or any other preferred catalog for install. And likewise for the RsyncOSXsched-version.dmg.
![](/images/RsyncOSX/master/install/install.png)
RsyncOSX is installed and used at your own risk. The developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Version 3.1.3 of rsync

See readme.txt within dmg file for how to manually install version rsync 3.1.3.

`rsync313.dmg: 568ccf4d0981223f51e1c54941bc6cbc87988ae8`

## Latest version of rsync

See more info about [the latest version of rsync and how to install it](/post/rsync/).

## Passwordless logins

Utilizing RsyncOSX for synchronize files and backup to remote servers require to setup  
[passwordless logins to remote servers](/post/remotelogins/).
