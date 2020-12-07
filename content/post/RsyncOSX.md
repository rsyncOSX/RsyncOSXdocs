+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "Install RsyncOSX"
tags = ["install","rsync version"]
categories = ["general information"]
description = "How to install RsyncOSX."
lastmod = "2020-09-23"
+++
RsyncOSX is released in [version 6.5.2 (4 December 2020)](https://github.com/rsyncOSX/RsyncOSX/releases/tag/v6.5.2). It is not required to install the menu app (RsyncOSXsched.app). The menu app is for executing [scheduled tasks](/post/scheduletasks) only. RsyncOSX is [signed and notarized](/post/notarized/).

## Install

The command

`shasum -a 256 ~/pathtodownload/RsyncOSX-version.dmg`

will print the shasum for the .dmg file. For your own safety verify the shasums.

`RsyncOSX 6.5.2.dmg: 995b21a2835a7cb4256b776ac842de12ecfc4694c70b8e3b8b4e164d91837681`  
`RsyncOSXsched 6.5.1.dmg: f622e5dbf56c45b48d9dc4dbd46e7d4ae4594fd6a77c090c204f9c676df7c3c6`

To install RsyncOSX open the downloaded RsyncOSX-version.dmg file. Drag the RsyncOSX icon to the default `/Applications` catalog or any other preferred catalog for install. And likewise for the RsyncOSXsched-version.dmg.
![](/images/RsyncOSX/master/install/install.png)
RsyncOSX is installed and used at your own risk. The developer accepts no responsibility for any errors, omissions or loss of data by using the application.

## Latest version of rsync

See more info about [the latest version of rsync and how to install it](/post/rsync/).

## Passwordless logins

Utilizing RsyncOSX for synchronize files and backup to remote servers require to setup  
[passwordless logins to remote servers](/post/remotelogins/).

## Homebrew

RsyncOSX can also be installed by Homebrew: `brew cask install rsyncosx`.
