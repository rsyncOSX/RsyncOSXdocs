+++
author = "Thomas Evensen"
date = "2020-04-16"
title =  "Combine and RsyncOSX"
tags = ["combine"]
categories = ["synchronize"]
description = "Combine and RsyncOSX."
lastmod = "2021-05-30"
+++
This version is **not yet released**. RsyncOSX version 6.6.0 will be released as an update for users on **macOS Big Sur**. Some features of Combine in RsyncOSX require macOS Big Sur. The Combine code is from developing the SwiftUI based version RsyncUI.

The application with menu app is working, but there will be some more cleanup and refactor before release in a couple of weeks.

Combine is used in the following parts:

- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadUserConfigurationPLIST.swift) user configurtaions to permanent store
- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- read and convert [configurations](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadConfigurationsPLIST.swift) and [schedules](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadSchedulesPLIST.swift) PLIST to JSON
- [the process object](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ProcessCmd.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/TrimTwo.swift) from rsync process

The instructions below if for users who start version 6.6.0 and dont see any configurations. Configurations in PLIST format must be converted to JSON.

## Prepare for use

**Caution**: always do a backup of the configuration files before following the steps below. See [the settings](/post/userconfiguration/) for backup.

Check the about where RsyncOSX stores the configfiles:
```
/Users/thomas/.rsyncosx/macserialnumber
```
![](/images/RsyncOSX/master/combine/about.png)

If you dont see any configurations after start?

![](/images/RsyncOSX/master/combine/empty.png)

In the file menu choose Transform.

![](/images/RsyncOSX/master/combine/files.png)

Then choose Convert and the magic happens.

![](/images/RsyncOSX/master/combine/convert.png)

RsyncOSX will terminate itself after conversion of files. Restart and files are converted.

![](/images/RsyncOSX/master/combine/converted.png)
