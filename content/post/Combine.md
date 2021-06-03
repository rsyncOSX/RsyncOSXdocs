+++
author = "Thomas Evensen"
date = "2020-04-16"
title =  "Combine and RsyncOSX"
tags = ["combine"]
categories = ["synchronize"]
description = "Combine and RsyncOSX."
lastmod = "2021-05-30"
+++
This version is **not yet released**. RsyncOSX version 6.6.0 will be released as an update for users on **macOS Big Sur**.

This is a project of introducing Combine into RsyncOSX. It will be released sometime in either June or July 2021, a release candidate will be annouced within a few weeks. The app is working, only some QA before a release candidate.

What is the purpose of this project? In development of [RsyncUI](https://github.com/rsyncOSX/RsyncUI), I "discovered" the new declarative framework Combine. Combine is also a great framework and makes the code easy to write and easy to read. It is most likely that RsyncOSX will avaliable for some years and why not upgrade RsyncOSX to utilize Combine.

There are though some restrictions. In the Combine code for encode and write data to JSON file, the publiser requiere macOS BigSur or later. This release will only be avaliable for macOS BigSur and later.

Much of the code where Combine is used is shared with RsyncUI. There is still some minor parts of code which needs to be added or changed before a release. The work to delete old code and replace with Combine was done in a couple of hours an evening.

I will also refactor and clean up other parts of the code as well as part of this project.

Combine is used in the following code:

- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadUserConfigurationPLIST.swift) user configurations to permanent store
- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- read and convert [configurations](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadConfigurationsPLIST.swift) and [schedules](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ReadSchedulesPLIST.swift) from PLIST format to JSON format
- [the process object](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/ProcessCmd.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSXCombine/blob/main/RsyncOSX/TrimTwo.swift) from rsync process

The instructions below if for users who start version 6.6.0 and dont see any configurations. Configurations in PLIST format must be converted to JSON.

## Prepare for use

**Caution**: always do a backup of the configuration files before following the steps below. See [the settings](/post/userconfiguration/) for backup.

Check the about where RsyncOSX stores the configfiles:
```bash
/Users/thomas/.rsyncosx/macserialnumber
```
![](/images/RsyncOSX/master/combine/about.png)

If you dont see any configurations after start?

![](/images/RsyncOSX/master/combine/empty.png)

In the file menu choose Convert, then choose Convert again and the magic happens. RsyncOSX will **terminate itself** after conversion of files. Restart and files are converted.

![](/images/RsyncOSX/master/combine/converted.png)
