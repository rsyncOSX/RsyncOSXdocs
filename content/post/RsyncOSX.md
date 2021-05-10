+++
author = "Thomas Evensen"
date = "2020-04-23"
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2021-03-24"
+++
RsyncOSX is released in [version 6.5.8 (24 March 2021)](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.8). It is not required to install the menu app (RsyncOSXsched.app). The menu app is for executing [scheduled tasks](/post/scheduletasks) only. RsyncOSX is [signed and notarized](/post/notarized/).

## Install by Homebrew

RsyncOSX can be installed by homebrew - `brew install --cask rsyncosx`.

## Install by download

Download [the latest version form GitHub](https://github.com/rsyncOSX/RsyncOSX/releases). The command `shasum -a 256 ~/pathtodownload/RsyncOSX-version.dmg` will print the shasum for the .dmg file. For your own safety verify the shasums.

`RsyncOSX 6.5.8.dmg: 4f23be29b260a93e05a2b9abf2ac42419b918b455e664d12ed92663ee008ad4e`  
`RsyncOSXsched 6.5.8.dmg: 14703772cb5d115b5b4c68dc37e7432211c73462641765eb9be9afc33ecfd2b1`

To install RsyncOSX open the downloaded RsyncOSX-version.dmg file. Drag the RsyncOSX icon to the default `/Applications` catalog or any other preferred catalog for install. And likewise for the RsyncOSXsched-version.dmg.
![](/images/RsyncOSX/master/install/install.png)
RsyncOSX is installed and used at your own risk. The developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Latest version of rsync

See more info about [the latest version of rsync and how to install it](/post/rsync/).

## Passwordless logins

Utilizing RsyncOSX for synchronize files and backup to remote servers require to setup  
[passwordless logins to remote servers](/post/remotelogins/).
