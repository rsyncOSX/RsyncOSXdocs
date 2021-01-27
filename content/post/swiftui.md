+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-19"
+++
The views are **only with a few formatting** and the main objective is to test SwiftUI and establish a working MVC architecture. The major formatting part will come later. Probably is more than 90% of the code in the SwiftUI version reused code from RsyncOSX. Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state).

There are some adaptions of the model classes used from RsyncOSX. And I am also using the oportunity to fix some of the more convoluted and old parts of code.

- estimation and executing single tasks works
- estimating of all tasks works
- select, estimate and execute several tasks works
- progressviews works

The plan is to make the source open sometime in February 2021. For the moment it is a private repo on my [GitHub account](https://github.com/rsyncOSX/).

For the moment the main focus is the MVC architecture and organizing of the code. The arrangement and work on the UI part will come later. And that is one of the advantages of SwiftUI. SwiftUI is a framework for UI and compared to the Swift/Storyboard version the numbers of codeline to create the screens of the SwiftUI based version is very minimal. And it is very fun to code the UI in SwiftUI. As long as the overall design applies to the MVC pattern it is easy to rearrange the UI part.

**The views are only a test and the final UI will not look like this.**

Below are a few screendumps of the alpha version of the SwiftUI based version of RsyncOSX.If you have any comments or ideas please use [the discussion part for RsyncOSX](https://github.com/rsyncOSX/RsyncOSX/discussions).

## A few screenshots

The default view when starting the app. Select a new profile any time and the app reloads the data. **There is little UI formatting, e.g that is why the profile dropdown takes the full width.** The UI and navigation is written 100% in SwiftUI. The actual Swift code for execution is from the RsyncOSX repo (with some minor adjustments).

![](/images/RsyncOSX/master/swiftui/1.png)

Selecting the `Single tasks`, either estimate and execute or execute without estimating. After execution the output from rsync is presented. And again, the layout of the buttons and status labels will change, this is an alpha version with focus on the MVC architecture.

![](/images/RsyncOSX/master/swiftui/2.png)

Select and excute multiple tasks, either select or by estimating.

![](/images/RsyncOSX/master/swiftui/3.png)

View the logs.

![](/images/RsyncOSX/master/swiftui/4.png)
