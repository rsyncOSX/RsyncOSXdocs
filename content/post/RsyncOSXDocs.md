+++
author = "Thomas Evensen"
title = "RsyncOSX - a GUI for rsync"
date = "2022-05-09"
tags = ["overview"]
categories = ["general information"]
lastmod = "2022-05-09"
+++
*Some important information about development of RsyncOSX. There are two GUIs for rsync developed by me, RsyncUI and RsyncOSX. More info abot both apps on [my GitHub Readme file](https://github.com/rsyncOSX/RsyncOSX). New development is and has been since beginning av 2023, only for RsyncUI - the SwiftUI based GUI. RsyncOSX is maintained and bugfixes only.  If you are a new user I will recommend using RsyncUI.*

RsyncOSX is a pure *Swift* and *Storyboar* based macOS application utilizing the command line tool `rsync` for synchronizing files. It is `rsync` which executes the real synchronizing task, not RsyncOSX. RsyncOSX is a GUI only on top of rsync. RsyncOSX is signed and notarized by Apple.  

Check out  [the categories](/categories)  for information about other topics not linked to on this page.  RsyncOSX is built for *macOS Big Sur and later*.

## Before commencing use of RsyncOSX

See [the changelog](/post/changelog/) for updates. RsyncOSX is built as a Universal macOS Binary, which means it runs nativly on Apple Silicon and Intel-based Mac computers.  RsyncOSX can be installed by Homebrew by command

```bash
brew install --cask rsyncosx
```
or by downloading  [the latest version](https://github.com/rsyncOSX/RsyncOSX/releases). If installed by Homebrew, the shasum is automatically verified. If downloaded from GitHub please verify the shasum.

## Remote servers, passwordless logins and local disks

RsyncOSX can synchronize your data to remote servers on the Internet, servers on your local LAN and to local attached disk. If you only want to synchronize data to a local attached disk, connect the disk, add source and destination and you are ready for your first task. If you want to synchronize data to a server there is some more setup to do. If you have enabled passwordless login by ssh you only have to add login id, servername, source and destination and you are ready to synchronize. If you have not enabled passwordless login, there are some more actions required before your first task.

## New users

The first time RsyncOSX starts, it presents a link to [important](/post/important/) information. There is also info about the [latest version of rsync](/post/rsync/) to install.

{{< figure src="/images/start/firsttask.png" alt="" position="center" style="border-radius: 8px;" >}}

RsyncOSX can be used in parallel with RsyncOSX. The catalog for storing configuration files is `$HOME/.rsyncosx/macserialnumber/`. RsyncOSX and RsyncOSX do not share user settings, e.g, like enabling version 3.x of rsync, has to be set in both apps.

## Aborting a task

Please be aware it is an external task not controlled by RsyncOSX, which executes the command line tool `rsync`. RsyncOSX is monitoring the task for progress and termination. The user can at any time abort a task. Please let the abort to finish and cleanup properly before starting a new task. It might take a few seconds. If not, the apps might become unresponsive.

## RsyncUI vs RsyncOSX

For the moment, there are more users of RsyncOSX than of RsyncUI. But the number of users of RsyncUI is growing. And Apple is clear: SwiftUI, which RsyncUI is developed by, is the future.  And RsyncUI has a few more features than RsyncOSX. RsyncOSX is still supported, but only issues are fixed and there are no new features. Last  update of RsyncOSX was in april 2023. 

*If you are on macOS Sonoma, my recommendation is to use RsyncOSX, not RsyncOSX.* 

## New tasks, verify and synchronizing data

After  [adding ](/post/addconfigurations/) a task, a double click on [task](/post/singletask/) will execute a simulated run or what is called a `--dry-run`. Verify the output from rsync by opening the log, top left icon on the sidebar of RsyncOSX, either ahead or after the simulated run. For more experienced users of rsync, select the new task and press the `Command` button. Copy and paste the `Synchronize` string into a terminal view for verification of the added task. The rsync command includes the `--dry-run` parameter as default within this view.

Always verify, by a `--dry-run`, the result of a new task before executing it.
