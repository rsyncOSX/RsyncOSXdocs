+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-02-10"
+++
The development commenced in December 2020 and the next release of RsyncOSX will be sometime before summer 2021. The next version is build for **macOS Big Sur** only.

SwiftUI is **a framework for UI**. Compared to a Swift, Storyboard and View Controllers application, the numbers of codelines to create the UI with SwiftUI is minimal. Programming the UI in SwiftUI is **declarative programming** and not imperativ. Only the UI is coded in SwiftUI. The code for the model part is traditional Swift development.

## Resources to learn SwiftUI

There are a lot of resources to learn SwiftUI. Google, Stack Overflow, YouTube and GitHub are amongst the most used resources. I am also following a few blogs like:

- Paul Hudson´s, [Hacking With Swift](https://www.hackingwithswift.com/)
- John Sundell´s, [Swift by Sundell](https://swiftbysundell.com/)
- Sean Allen´s [swift news](https://github.com/SAllen0400/swift-news)
- Dave Werver´s [iOS Dev Weekly](https://iosdevweekly.com/)
- [Apple tutorials about developing in SwiftUI](https://developer.apple.com/tutorials/app-dev-training)

And to be honest, **the future of RsyncOSX is SwiftUI**. Coding in **SwiftUI is very fun**. The code for UI might be minimal and separated from the Model (MVC). And by hiding application logic and actions in properties, functions and closures will simplify the code and make more easy to read. Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state). Single source of truth is also an important part of the MVC architecture.

## What is in the alpha versions

UI = [user interface](https://en.wikipedia.org/wiki/User_interface)

There is lot of reused code in the next version, but all of the code for UI is new. That means the UI is also changed, to the better in my opinion. The reused code is classes like reading and saving data to permanent store, execution of tasks, logging of execution of tasks, scheduling and so on. All the UI is new and implemented in SwiftUI. There is **no administration** (create, edit and delete) of configurations, schedules and logs in the alpha version yet. The alpha version reads the current default profile and other profiles created in RsyncOSX. And it reads all settings in user profile. If you want to test the alpha version, please use RsyncOSX to **administrate** (create, edit and delete) configurations.

The following is in the alpha version:

**The alpha version can be used alongside the existing version of RsyncOSX.**

- reading configurations, either as JSON or PLIST files (set in RsyncOSX userconfig)
- estimation and executing single tasks works, all three types of tasks
- estimating and execution of all and selected tasks
- executing (no estimation) of selected or all tasks
- view output from rsync, either from singletasks or aggregated data from multiple tasks
- view logfile
- the error handling is refactored and enhanced compared to the current version

To summarize most of the executing part is in code and it work.

## What is not the alpha version

The following is **not yet** part of the alpha version, **there is no**:

- setting user selected values, but the alpha version reads all user settings
- administration (create, edit and delete) of **configurations**, **schedules** and **logs**
- restore of data
- execution of shellout tasks, configurations with pre and post shell scripts
- administration of parameters to rsync
- administration of snapshot tasks
- shortcut codes for various tasks
- no start or stop of the menu app for scheduling of tasks
- not yet localized, but prepared for it

All the above will gradually be implemented in the new version.

## The source code

The source is available on my [GitHub account](https://github.com/rsyncOSX/RsyncSwiftUI). If you have any comments or ideas please use [the discussion part for RsyncSwiftUI](https://github.com/rsyncOSX/RsyncSwiftUI/discussions).

## The Alpa version 0.1

**The UI will change, but the overall structure of the new version will be like the views below. The applications is developed every day and there will be changes.**

Below are a couple of screendumps of the alpha version of the SwiftUI based version of RsyncOSX. The default view when starting the app. Select a new profile any time and the app reloads the data.

![](/images/RsyncOSX/master/swiftui/1.png)

The start might be `Multiple tasks`. Choose `Estimate` and then `Execute` after estimation is completed. The estimation marks tasks with data for syncronizing. Or go for all tasks.

![](/images/RsyncOSX/master/swiftui/2.png)

If you want more controle, select `Single tasks`. Either `Estimate` and `Execute` or `Now`, which executes without estimation.

![](/images/RsyncOSX/master/swiftui/3.png)

Viewing parameters to rsync.

![](/images/RsyncOSX/master/swiftui/4.png)
