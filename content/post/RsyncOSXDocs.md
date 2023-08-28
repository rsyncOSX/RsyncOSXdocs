+++
author = "Thomas Evensen"
title = "RsyncOSX - a GUI for rsync"
date = "2022-05-09"
tags = ["overview"]
categories = ["general information"]
lastmod = "2022-05-09"
+++

RsyncOSX is a pure Swift based macOS application utilizing the command line tool `rsync` for synchronizing files. It is `rsync`  which executes the actual synchronized task. RsyncOSX is a GUI only on top of rsync. RsyncOSX is *signed* and *notarized* by Apple.There are no third party libraries included in the code. There are three source codes not developed by me included in the code. The third part of the source code is only for support and not critical if removed.

Check out  [the categories](/categories)  for information about other topics not linked to on this page.

## Before commencing use of RsyncOSX

[RsyncOSX](https://github.com/rsyncOSX/RsyncOSX/releases)  is compiled for *macOS Big Sur* and later. See the [the changelog](/post/changelog/) for updates. RsyncOSX is built as a Universal macOS Binary and runs nativly on Apple Silicon and Intel-based Mac computers. RsyncOSX can be installed by homebrew by command:

```bash
brew install --cask rsyncosx
```

or by downloading  [the latest version](https://github.com/rsyncOSX/RsyncOSX/releases). If installed by homebrew, the shasum is automatically verified. If downloaded from GitHub please verify the shasum.

## Remote servers, passwordless logins and local disks

RsyncOSX can synchronize your data to either remote servers on the Internet and local LAN, or to local attached disks. If you only want to synchronize data to a local attached disk, connect the disk and just add the source and destination and you are ready for your first task. If you want to synchronize data to remote servers, there is some more setup to do. If you already have enabled *passwordless login* by ssh you only have to add login id and servername, the source and destination and you are ready. If you have not enabled passwordless login, there are some more actions required before your first task.

## New users

The first time RsyncOSX starts, it presents a link to  [important information](/post/important/). There is also info about the latest version of rsync to install.

{{< figure src="/images/RsyncOSX/master/start/start.png" alt="" position="center" style="border-radius: 8px;" >}}

The error at the bottom of the view is only RsyncOSX complaining about not finding the default file for stored tasks. The error disappears as soon as the first task is added.

## Aborting a task

Please be aware it is an external task not controlled by RsyncOSX, which executes the command line tool rsync. RsyncOSX is monitoring the task for progress and termination. The user can at any time abort a task . Please let the abort to finish and cleanup properly before starting a new task. It might take a few seconds. If not, the apps might become unresponsive.

## RsyncOSX vs RsyncUI

For the moment, there are more users of RsyncOSX than RsyncUI. But the number of users of RsyncUI is growing. And Apple is clear, SwiftUI, which RsyncUI is developed by, is the future. This means that most of my development is now on RsyncUI. RsyncOSX is still supported, but only issues are fixed and no new features.

RsyncUI and RsyncOSX share most of the code for the model components. The main differences between the two apps are the user interface (UI) and how the UI is built. RsyncUI is developed utilizing SwiftUI. RsyncOSX is developed utilizing Storyboards. Both apps utilize another great declarative library, Combine, developed by Apple and JSON files for storing tasks, logrecords and user configuration.

## New tasks; verifying and synchronizing data

After  [adding ](/post/addconfigurations/) a task, a double click on [task](/post/singletask/) will execute a simulated run or what is called a `--dry-run`. Verify the output from rsync by opening the log, top left icon on the sidebar of RsyncOSX, either ahead or after the simulated run.

For more experienced users of rsync, select the new task and press the `Command` button. Copy and paste the `Synchronize` string into a terminal view for verification of the added task. The rsync command includes the `--dry-run` parameter as default within this view.

Always verify, by a `--dry-run`, the result of a new task before executing it.
