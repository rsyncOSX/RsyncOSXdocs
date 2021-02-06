+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-31"
+++
SwiftUI is **a framework for UI**. Compared to a Swift (View Controllers) and Storyboard application, the numbers of codeline to create the UI is minimal. Programming the UI in SwiftUI is **declarative programming** and not imperativ. And for me that is a huge difference and it will take some time for me to adapt to the new programming paradigm. Only the UI is developed in SwiftUI and that means the SwiftUI version for RsyncOSX utilizing traditional Swift development for the model classes.

## Alpha version

I am using the alpha version on daily basis. It stable and it does what it is expected to do. The UI in the SwiftUI based version is changed, to the better, in my opinion. But it is an alpha version and there might be a bug or two. There will be released an alpha test version before end of February.

## Resources to learn SwiftUI

There are a lot of resources to learn SwiftUI. Google, Stack Overflow, YouTube and GitHub are amongst the most used resources. I am also following a few blogs like:

- Paul Hudson´s, [Hacking With Swift](https://www.hackingwithswift.com/)
- John Sundell´s, [Swift by Sundell](https://swiftbysundell.com/)
- Sean Allen´s [swift news](https://github.com/SAllen0400/swift-news)
- Dave Werver´s [iOS Dev Weekly](https://iosdevweekly.com/)
- [Apple tutorials about developing in SwiftUI](https://developer.apple.com/tutorials/app-dev-training)

## The RsyncSwiftUI app

The views are with **some UI formatting** and the main objective for the moment is to establish a working MVC architecture for the SwiftUI based version of RsyncOSX. Probably is between 70% - 80% of the code in the SwiftUI version reused code from RsyncOSX. The reused code is classes like reading and saving data to permanent store, executing tasks, logging, scheduling and so on. All UI is and will be implemented in SwiftUI.

**And to be honest, the future of RsyncOSX is SwiftUI**. Coding in SwiftUI is fun. The code for UI might be very minimal and separated from the Model. And by hiding application logic and actions in properties and functions, will  simplify and make the code for UI minimal and more easy to read.

Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state). Single source of truth is also an important part of the MVC architecture.

There are some adaptions of the model classes used from RsyncOSX. And I am also using the oportunity to fix some of the more convoluted and old parts of code.

- estimation and executing single tasks works, all three types of tasks
- estimating of all and selected tasks works
- executing several or all tasks works
- progressviews works
- view output from rsync, either from singletasks or aggregated data from multiple tasks

The following is **not yet** part of the alpha version, **there is no**:

- automatic execution of tasks
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
