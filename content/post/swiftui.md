+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-19"
+++
The views below are **without formatting** and the main objective is to test SwiftUI and establish a working MVC architecture. The formatting part will come later. Probably is more than 90% of the code in the SwiftUI version reused code from RsyncOSX. Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state).

There are some adaptions of the model classes used from RsyncOSX. And I am also using the oportunity to fix some of the more convoluted and old parts of code.

- estimation and executing single tasks works
- estimating of all tasks works
- select, estimate and execute several tasks works

The plan is to make the source open sometime in February 2021. For the moment it is a private repo on my [GitHub account](https://github.com/rsyncOSX/). I do hope other developers can assist me on the code on the UI part.

For the moment the main focus is the MVC architecture and organizing of the code. The arrangement and work on the UI part will come later. And that is one of the advantages of SwiftUI. SwiftUI is a framework for UI and compared to the Swift/Storyboard version the numbers of codeline to create the screens of the SwiftUI based version is very minimal. And it is very fun to code the UI in SwiftUI. As long as the overall design applies to the MVC pattern it is easy to rearrange the UI part.

**The views are only a test and the final UI will not look like this.**

Below are a few screendumps of the alpha version of the SwiftUI based version of RsyncOSX.If you have any comments or ideas please use [the discussion part for RsyncOSX](https://github.com/rsyncOSX/RsyncOSX/discussions).

## A few screenshots

The default view when starting the app. Select a new profile any time and the app reloads the data. **There is no UI formatting, that is why the profile dropdown takes the full width.**

![](/images/RsyncOSX/master/swiftui/1.png)

Selecting the `Singletask`, either estimate and execute or execute without estimating. After execution the output from rsync is presented. And again, the layout of the buttons and status labels will change, this is an alpha version with focus on the MVC architecture.

![](/images/RsyncOSX/master/swiftui/2.png)
![](/images/RsyncOSX/master/swiftui/3.png)

Estimating in progress...

![](/images/RsyncOSX/master/swiftui/5.png)

The result of estimating, for the moment no labels only numbers...

![](/images/RsyncOSX/master/swiftui/6.png)

View the details of the configurations and schedules.

![](/images/RsyncOSX/master/swiftui/7.png)
![](/images/RsyncOSX/master/swiftui/8.png)
![](/images/RsyncOSX/master/swiftui/9.png)
![](/images/RsyncOSX/master/swiftui/10.png)
