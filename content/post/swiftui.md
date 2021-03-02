+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-03-02"
+++
The development commenced in December 2020 and the next release of RsyncOSX will be sometime before summer 2021. The next version is build for **macOS Big Sur** only.

The name of the new version is a working name. The code will be merged into the RsyncOSX repository when the new version is released.

SwiftUI is **a framework for UI**. Compared to a Swift, Storyboard and View Controllers application, the numbers of codelines to create the UI with SwiftUI is minimal. Programming the UI in SwiftUI is **declarative** and not imperativ. The code for the model part is traditional Swift code.

And to be honest, **the future of RsyncOSX is SwiftUI**. And it is **really fun to code in SwiftUI**. The code for UI is minimal and separated from the Model (MVC). By hiding application logic and actions in properties, functions and closures will simplify the code and make more easy to read. The declarative paradigm makes the code for the UI clean and easy to follow.

## Prerelease (test) of new version

The final version is not to be released before closer to summer 2021. Most of the core basic functions like executing tasks, compute the parameters to rsync are reused code from the current version. And most of the executing part within the prerelase is stable and working.

The prerelase is temporary removed. A new and enhanced version will be released later in March 2021.

## What is working

There are lot of reused code within the Model part, but all of the code for UI is new. That means the UI is also changed, to the better in my opinion. The reused code is classes like reading and saving data to permanent store, execution of tasks, logging of execution of tasks, scheduling and so on. The prerelease reads the current default profile and other profiles created by RsyncOSX. **The prerelease can be used alongside the existing version of RsyncOSX.**

The following is implemented (updated as new features are implemented):

- reading configurations, either as JSON or PLIST files
- estimation and executing single tasks
- estimating and execution of all and selected tasks
- executing (no estimation) of selected or all tasks
- view output from rsync, either from singletasks or aggregated data from multiple tasks
- view logfile
- the error handling is refactored and enhanced compared to the current version
- setting user selected values (user settings)
- setting ssh global values
- add nd valdidate new configurations
- delete configurations
- update configurations
- view logs, view snapshots, tag snapshots

To summarize most of the executing part is in code and it works.

## What is not yet implemented

The following is **not yet** implemented:

- administration (create, edit and delete) of **schedules** and **logs**
- restore of data
- execution of **shellout tasks**, configurations with pre and post shell scripts
- administration of parameters to rsync
- administration of snapshot tasks
- shortcut codes for various tasks
- no start or stop of the menu app for scheduling of tasks
- not yet localized, but prepared for it

All the above will gradually be implemented in the new version.

## The source code

The source is available on my [GitHub account](https://github.com/rsyncOSX/RsyncSwiftUI). If you have any comments or ideas please use [the discussion part for RsyncSwiftUI](https://github.com/rsyncOSX/RsyncSwiftUI/discussions).

## A few screenshots

**The UI will change as the development continues, but the overall structure of the new version will be like the views below.** The default view when starting the app. Select a new profile any time and the app reloads the data.

![](/images/RsyncOSX/master/swiftui/1.png)

The start might be `Multiple tasks`. Choose `Estimate` and then `Execute` after estimation is completed. The estimation marks tasks with data for syncronizing. Or just go for all tasks, no estimation and execute direct. An example of how easy it is too create the UI is the [Estimation View](https://github.com/rsyncOSX/RsyncSwiftUI/blob/main/RsyncSwiftUI/Views/Multitask/EstimationView.swift). There are approx only 60 lines of code for the layout of the estimation view (below).

![](/images/RsyncOSX/master/swiftui/2.png)

If you want more control, select `Single tasks`. Choose either `Estimate` and `Execute` or `Now`, which executes without estimation.

![](/images/RsyncOSX/master/swiftui/3.png)

Viewing the parameters to rsync for one task. The user can (when the app is released) set any setting to rsync.

![](/images/RsyncOSX/master/swiftui/4.png)

Within the `Multiple tasks` menu selecting `Estimate` kicks off estimating of all tasks. Any task with data for syncronizing, transfer and delete, are marked.

![](/images/RsyncOSX/master/swiftui/estimating.png)

Selecting the `Execute` kicks off the actual syncronizing tasks. For each task there is presented the progress. There is also presented the overall progress of number of tasks executed.

![](/images/RsyncOSX/master/swiftui/execute.png)

Showing logs for one task.

![](/images/RsyncOSX/master/swiftui/logs.png)

Some user settings.

![](/images/RsyncOSX/master/swiftui/settings.png)

SSH settings and a few others.

![](/images/RsyncOSX/master/swiftui/ssh.png)

## Resources to learn SwiftUI

There are a lot of resources to learn SwiftUI. Google, Stack Overflow, YouTube and GitHub are amongst the most used resources. I am also following a few blogs like:

- Paul Hudson´s, [Hacking With Swift](https://www.hackingwithswift.com/)
- John Sundell´s, [Swift by Sundell](https://swiftbysundell.com/)
- Sean Allen´s [swift news](https://github.com/SAllen0400/swift-news)
- Dave Werver´s [iOS Dev Weekly](https://iosdevweekly.com/)
- [Apple tutorials about developing in SwiftUI](https://developer.apple.com/tutorials/app-dev-training)

Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state). Single source of truth is also an important part of the MVC architecture.
