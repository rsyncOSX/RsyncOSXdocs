+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Combine and RsyncOSX"
tags = ["combine"]
categories = ["develop"]
lastmod = "2021-05-30"
+++
In development of [RsyncUI](https://github.com/rsyncOSX/RsyncUI), I learned about the new declarative framework Combine. Combine is a great framework and makes the code easy to write and easy to read. In the Combine code for encode and write data to JSON file, the publisher requiere **macOS BigSur** and later.

Much of the code where Combine is used is shared with RsyncUI. Combine is utilized in the following parts of the app:

- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadUserConfigurationPLIST.swift) user configurations from permanent store
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- read and convert [configurations](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadConfigurationsPLIST.swift) and [schedules](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadSchedulesPLIST.swift) from PLIST format to JSON format
- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/TrimTwo.swift) from rsync process
