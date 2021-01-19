+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-19"
+++
The views below are **without formatting** and the main objective is to test SwiftUI and establish a working MVC architecture. The formatting part will come later. Probably is more than 90% of the code in the SwiftUI version reused code from RsyncOSX. The SwiftUI part, primarly the UI and navigation is new.

There is some adaption of the model classes used from RsyncOSX. And I am also using the oportunity to fix some of the more convoluted and old parts of code.

- estimation and executing single tasks works
- estimating of all tasks works
- updating configurations and logging after executing works
- next to work on is execution of all estimated tasks

The plan is to make the source open sometime in February 2021. I do hope other developers can assist me on the code on the UI part. For the moment the main focus is the MVC architecture and organizing of the code. The arrangement and work on the UI part will come later. And that is one of the advantages of SwiftUI. The UI part is a few lines of code and as long as the overall design applies to the MVC pattern it is easy to rearrange the UI part.

**The views are only a test and the final UI will not look like this.**

Below is a few screendumps of the alpha version of the SwiftUI based version of RsyncOSX. Only execution of singetasks and estimation of all tasks are implemented. SwiftUI is a framework for UI and compared to the Swift/Storyboard version the numbers of codeline to create the screens of the SwiftUI based version is very minimal. And it is very fun to code the UI in SwiftUI.

## A few screenshots

![](/images/RsyncOSX/master/swiftui/1.png)
![](/images/RsyncOSX/master/swiftui/2.png)
![](/images/RsyncOSX/master/swiftui/3.png)
![](/images/RsyncOSX/master/swiftui/4.png)
![](/images/RsyncOSX/master/swiftui/5.png)
![](/images/RsyncOSX/master/swiftui/6.png)
![](/images/RsyncOSX/master/swiftui/7.png)
![](/images/RsyncOSX/master/swiftui/8.png)
![](/images/RsyncOSX/master/swiftui/9.png)
![](/images/RsyncOSX/master/swiftui/10.png)
