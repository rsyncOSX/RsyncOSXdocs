+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2020-09-23"
+++
RsyncOSX is released in [version 6.5.7 (19 March 2021)](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.7). It is not required to install the menu app (RsyncOSXsched.app). The menu app is for executing [scheduled tasks](/post/scheduletasks) only. RsyncOSX is [signed and notarized](/post/notarized/).

## Install by Homebrew

RsyncOSX can be installed by homebrew - `brew install --cask rsyncosx`.

## Install by download

Download [the latest version form GitHub](https://github.com/rsyncOSX/RsyncOSX/releases). The command `shasum -a 256 ~/pathtodownload/RsyncOSX-version.dmg` will print the shasum for the .dmg file. For your own safety verify the shasums.

`RsyncOSX 6.5.7.dmg: b123c4c4c70944cdf0f86d867e815710ea461b62d109d8974035ad6b05621e59`  
`RsyncOSXsched 6.5.7.dmg: 3e76b41c93c36a43c1c02d57c4fe302b7efacc9fc9e05c1bcb8221f5668eeccd`

To install RsyncOSX open the downloaded RsyncOSX-version.dmg file. Drag the RsyncOSX icon to the default `/Applications` catalog or any other preferred catalog for install. And likewise for the RsyncOSXsched-version.dmg.
![](/images/RsyncOSX/master/install/install.png)
RsyncOSX is installed and used at your own risk. The developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Latest version of rsync

See more info about [the latest version of rsync and how to install it](/post/rsync/).

## Passwordless logins

Utilizing RsyncOSX for synchronize files and backup to remote servers require to setup  
[passwordless logins to remote servers](/post/remotelogins/).
