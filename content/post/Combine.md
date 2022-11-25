+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Combine, async and await"
tags = ["combine","asynchronous execution"]
categories = ["develop"]
lastmod = "2021-05-30"
+++
RsyncOSX is developed utilizing default Swift and Swift libraries. Swift is a functional programming language, but some parts of RsyncOSX utilizes Combine which is a declarative framework.

# Combine

Combine makes the code easy to write and easy to read. In the Combine code for encode and write data to JSON file, the publisher requiere **macOS BigSur** and later. Combine is utilized in the following parts of the app:

- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadUserConfigurationJSON.swift) user configurations from permanent store
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/TrimTwo.swift) from rsync process

# Asynchronous execution

Asynchronous execution of tasks are a key component of RsyncOSX. There are two methods for asynchronous execution within RsyncOSX. One is utilizing callback functions or completion handler, which trigger next action when task is completed. The second is utilize Swifts `async` and `await`. Utilizing `async` and `await` makes the code simpler and cleaner. The need for callback functions are reduced.  And lesser code is better code.

There are two versions of the process object:

- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift)
- [the async process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessAsync.swift)

The difference between those two objects are minor, the async version marks the function for execution with keyword `async`. Calling the `async` require the `await` keyword. 

- [the await keyword](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ExecuteTaskNow.swift)
