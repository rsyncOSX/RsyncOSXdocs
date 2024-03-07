+++
author = "Thomas Evensen"
title = "RsyncOSX - a GUI for rsync"
date = "2022-05-09"
tags = ["overview"]
categories = ["general information"]
lastmod = "2022-05-09"
+++
*Some important information about development of RsyncOSX. There are two GUIs for rsync developed by me, RsyncUI and RsyncOSX. More info abot both apps on [my GitHub Readme file](https://github.com/rsyncOSX/RsyncOSX). New development is and has been since beginning av 2023, only for RsyncUI - the SwiftUI based GUI. RsyncOSX is maintained and bugfixes only.  If you are a new user I will recommend using RsyncUI.*

RsyncOSX is a pure *Swift* and *Storyboard* based macOS application utilizing the command line tool `rsync` for synchronizing files. It is `rsync` which executes the real synchronizing task, not RsyncOSX. RsyncOSX is a GUI only on top of rsync. RsyncOSX is signed and notarized by Apple.  

## Before commencing use of RsyncOSX

See [the changelog](/post/changelog/) for updates. RsyncOSX is built as a Universal macOS Binary, which means it runs nativly on Apple Silicon and Intel-based Mac computers.  RsyncOSX can be installed by Homebrew by command

```bash
brew install --cask rsyncosx
```
or by downloading  [the latest version](https://github.com/rsyncOSX/RsyncOSX/releases). If installed by Homebrew, the shasum is automatically verified. If downloaded from GitHub please verify the shasum.

##  Local attached disks, remote servers and passwordless logins

RsyncOSX can synchronize your data to local attached disk, remote servers on the Internet and servers on your local LAN. If you only want to synchronize data to a local attached disk, connect the disk, add source and destination and you are ready for your first task. If you want to synchronize data to a server, on Internet or your local LAN, there is some more setup to do. If you have enabled passwordless login by ssh-keys you only have to add source, destination, login id and servername and you are ready to synchronize. If you have not enabled passwordless login, there are some more actions required before your first task.

## New users

The first time RsyncOSX starts, it presents a link to [important](/post/important/) information. There is also info about the [latest version of rsync](/post/rsync/) to install.

{{< figure src="/images/RsyncOSX/master/start/start.png" alt="" position="center" style="border-radius: 8px;" >}}

The catalog for [storing configuration](/post/configfiles/) files is `$HOME/.rsyncosx/macserialnumber/`.

## Aborting a task

Please be aware it is an external task not controlled by RsyncOSX, which executes the command line tool `rsync`. RsyncOSX is monitoring the task for progress and termination. The user can at any time abort a task. Please let the abort to finish and cleanup properly before starting a new task. It might take a few seconds. If not, the apps might become unresponsive.

## RsyncUI vs RsyncOSX

Which application should I use? Both applications do the same job, but RsyncUI is more feature-rich, and the GUI, including navigation, is better. **Are you on macOS Sonoma?** Go for RsyncUI. And for the last year and years to come, all development has been and will be within RsyncUI. RsyncOSX is maintained, but only for bug fixes.

## New tasks, verify and synchronizing data

After  [adding ](/post/addconfigurations/) a task, a double click on [task](/post/singletask/) will execute a simulated run or what is called a `--dry-run`. Verify the output from rsync by opening the log, top left icon on the sidebar of RsyncOSX, either ahead or after the simulated run. For more experienced users of rsync, select the new task and press the `Command` button. Copy and paste the `Synchronize` string into a terminal view for verification of the added task. The rsync command includes the `--dry-run` parameter as default within this view. Always verify, by a `--dry-run`, the result of a new task before executing it.
