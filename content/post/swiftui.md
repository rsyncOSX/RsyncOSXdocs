+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-31"
+++
SwiftUI is **a framework for UI**. Compared to a Swift (View Controllers) and Storyboard application, the numbers of codelines to create the UI is minimal. Programming the UI in SwiftUI is **declarative programming** and not imperativ. Only the UI is coded in SwiftUI. The code for the model part is traditional Swift development.

## Resources to learn SwiftUI

There are a lot of resources to learn SwiftUI. Google, Stack Overflow, YouTube and GitHub are amongst the most used resources. I am also following a few blogs like:

- Paul Hudson´s, [Hacking With Swift](https://www.hackingwithswift.com/)
- John Sundell´s, [Swift by Sundell](https://swiftbysundell.com/)
- Sean Allen´s [swift news](https://github.com/SAllen0400/swift-news)
- Dave Werver´s [iOS Dev Weekly](https://iosdevweekly.com/)
- [Apple tutorials about developing in SwiftUI](https://developer.apple.com/tutorials/app-dev-training)

**And to be honest, the future of RsyncOSX is SwiftUI**. Coding in SwiftUI is fun. The code for UI might be very minimal and separated from the Model. And by hiding application logic and actions in properties and functions, will  simplify and make the code for UI minimal and more easy to read. Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state). Single source of truth is also an important part of the MVC architecture.

## What is in the alpha versions

I am using the alpha version on daily basis. It is quite stable and it does what it is expected to do.

Probably is between 60% - 70% of the code in the SwiftUI version reused code from RsyncOSX. The reused code is classes like reading and saving data to permanent store, execution of tasks, logging of execution of tasks, scheduling and so on. All the UI is implemented in SwiftUI. There is **no administration** (create, edit and delete) of configurations, schedules and logs in the alpha version yet. The alpha version reads the current default profile and other profiles created in RsyncOSX. And it reads all settings in user profile. If you want to test the alpha version, please use RsyncOSX to **administrate** (create, edit and delete) configurations.

I am using the alpha version on daily basis. The UI in the SwiftUI based version is changed to the better. But it is still an alpha version and there might be a bug or two. The following is in the alpha version.

**The alpha version can be used alongside the existing version of RsyncOSX.**

- reading existing user setting and configurations, either as JSON or PLIST files (set in user config)
- estimation and executing single tasks works, all three types of tasks
- estimating and execution of all and selected tasks works
- executing of selected or all tasks works
- progressviews works
- view output from rsync, either from singletasks or aggregated data from multiple tasks

To summarize most of the executing part is in code. There will still be some QA before the alpha is released before end of February 2021.

## What is not the alpha version

The following is **not yet** part of the alpha version, **there is no**:

- setting user selected values, but the alpha version reads all user settings
- administration (create, edit and delete) of **configurations**, **schedules** and **logs**
- restore of data
- execution of shellout tasks, configurations with pre and post shell scripts
- administration of parameters to rsync
- administration of snapshot tasks
- shortcut codes for various tasks

All the above will gradually be implemented in the new version.

## The source code

The source is available on my [GitHub account](https://github.com/rsyncOSX/RsyncSwiftUI). If you have any comments or ideas please use [the discussion part for RsyncSwiftUI](https://github.com/rsyncOSX/RsyncSwiftUI/discussions).

## A few screenshots

**The UI will change, but the overall structure of the new version will be like the views below.**

Below are a couple of screendumps of the alpha version of the SwiftUI based version of RsyncOSX. The default view when starting the app. Select a new profile any time and the app reloads the data.

![](/images/RsyncOSX/master/swiftui/1.png)

Selecting the `Single tasks`, either estimate and execute or execute without estimating. After execution the output from rsync is presented. And again, the layout of the buttons and status labels will change, this is an alpha version with focus on the MVC architecture.

![](/images/RsyncOSX/master/swiftui/2.png)

Either all or selected tasks and excute.

![](/images/RsyncOSX/master/swiftui/3.png)

Show me the actual rsync command.

![](/images/RsyncOSX/master/swiftui/4.png)

The about.

![](/images/RsyncOSX/master/swiftui/7.png)
