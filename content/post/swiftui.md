+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-28"
+++

SwiftUI is **a framework for UI**. Compared to a Swift/Storyboard application, the numbers of codeline to create the UI is minimal. There are also several other advantages utilizing SwiftUI, but that is not part of this info.

The views are with **some UI formatting** and the main objective for the moment is to establish a working MVC architecture for the SwiftUI based version of RsyncOSX. Probably is between 80% - 90% of the code in the SwiftUI version reused code from RsyncOSX. The reused code is classes like reading and saving data to permanent store, executing tasks, logging, scheduling and so on. All UI is and will be implemented in SwiftUI.

And I have also just commenced learning SwiftUI and that will also take some time.

**And to be honest, the future of RsyncOSX is SwiftUI**. Coding in SwiftUI is fun. The code for UI might be very minimal and separated from the Model. And by hiding application logic and actions in properties and functions, will  simplify and make the code for UI minimal and more easy to read.

Another important aspect of SwiftUI is the [single source of truth](https://developer.apple.com/documentation/swiftui/managing-user-interface-state). Single source of truth is also an important part of the MVC architecture.

There are some adaptions of the model classes used from RsyncOSX. And I am also using the oportunity to fix some of the more convoluted and old parts of code.

- estimation and executing single tasks works
- estimating of all tasks works
- select, estimate and execute several tasks works
- progressviews works

The plan is to make the source open sometime in February 2021. For the moment it is a private repo on my [GitHub account](https://github.com/rsyncOSX/).

**The UI will change, but the overall structure of the new version will be like the views below.**

Below are a few screendumps of the alpha version of the SwiftUI based version of RsyncOSX.If you have any comments or ideas please use [the discussion part for RsyncOSX](https://github.com/rsyncOSX/RsyncOSX/discussions).

## A few screenshots

The default view when starting the app. Select a new profile any time and the app reloads the data.

![](/images/RsyncOSX/master/swiftui/1.png)
![](/images/RsyncOSX/master/swiftui/2.png)

Selecting the `Single tasks`, either estimate and execute or execute without estimating. After execution the output from rsync is presented. And again, the layout of the buttons and status labels will change, this is an alpha version with focus on the MVC architecture.

![](/images/RsyncOSX/master/swiftui/3.png)

Select and excute multiple tasks, select and execute.

![](/images/RsyncOSX/master/swiftui/4.png)

View the logs and schedules.

![](/images/RsyncOSX/master/swiftui/5.png)

![](/images/RsyncOSX/master/swiftui/6.png)

The about.

![](/images/RsyncOSX/master/swiftui/7.png)
