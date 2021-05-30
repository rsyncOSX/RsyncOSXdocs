+++
author = "Thomas Evensen"
date = "2020-04-16"
title =  "Combine and RsyncOSX"
tags = ["combine"]
categories = ["synchronize"]
description = "Combine and RsyncOSX."
lastmod = "2020-12-13"
+++
This version is **not yet released**. RsyncOSX version 6.6.0 will be released as an update for users on **macOS Big Sur**. Some features of Combine in RsyncOSX require macOS Big Sur.

Combine is used in the following code:

- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadUserConfigurationPLIST.swift) user configurtaions to permanent store
- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- read and convert [configurations](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadConfigurationsPLIST.swift) and [schedules](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadSchedulesPLIST.swift) PLIST to JSON
- [the process object](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ProcessCmd.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/TrimTwo.swift) from rsync process

The instrcutions below if for users who start version 6.6.0 and dont see any configurations. Configurations in PLIST format must be converted to JSON.

## Prepare for use

Check the about where RsyncOSX stores the configfiles:
```
/Users/thomas/.rsyncosx/macserialnumber
```
![](/images/RsyncOSX/master/combine/about.png)
![](/images/RsyncOSX/master/combine/empty.png)
![](/images/RsyncOSX/master/combine/files.png)
![](/images/RsyncOSX/master/combine/convert.png)
![](/images/RsyncOSX/master/combine/converted.png)
