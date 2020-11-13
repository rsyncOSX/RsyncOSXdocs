+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2020-09-23"
+++
RsyncOSX is released in [version 6.5.0 (12 November 2020)](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.0). It is not required to install the menu app (RsyncOSXsched.app). The menu app is for executing [scheduled tasks](/post/scheduletasks) only. RsyncOSX is [signed and notarized](/post/notarized/).

## Install

The command

`shasum ~/pathtodownload/RsyncOSX-version.dmg`

will print the shasum for the .dmg file. For your own safety verify the shasums.

`RsyncOSX 6.5.0.dmg: fee95ac248b6734916b9a1c458a1e8ee8d47b677`  
`RsyncOSXsched 6.5.0.dmg: 173a490e9fe39473c297f048de59ab22cfcf959e`

To install RsyncOSX open the downloaded RsyncOSX-version.dmg file. Drag the RsyncOSX icon to the default `/Applications` catalog or any other preferred catalog for install. And likewise for the RsyncOSXsched-version.dmg.
![](/images/RsyncOSX/master/install/install.png)
RsyncOSX is installed and used at your own risk. The developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Latest version of rsync

See more info about [the latest version of rsync and how to install it](/post/rsync/).

## Passwordless logins

Utilizing RsyncOSX for synchronize files and backup to remote servers require to setup  
[passwordless logins to remote servers](/post/remotelogins/).

## Homebrew

RsyncOSX can also be installed by [Homebrew](https://brew.sh/index_nb): `brew cask install rsyncosx`.
