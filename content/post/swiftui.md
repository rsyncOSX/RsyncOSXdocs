+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "SwiftUI"
tags = ["swiftui"]
categories = ["swiftui"]
description = "Some info about SwiftUI version of RsyncOSX"
lastmod = "2021-01-15"
+++
The views below is without formatting and the main objective is to test SwiftUI and establish a working MWM architecture. The formatting part will come later. Probably is more than 90% of the code in the SwiftUI version reused code from RsyncOSX. The SwiftUI part, primarly the UI and navigation part is new.

**The views are only a test and the final UI will not look like this.**

Below is three screendumps of the alpha version of the SwiftUI based version of RsyncOSX. SwiftUI is a framework for UI and compared to the Swift/Storyboard version the numbers of codeline to create the screens of the SwiftUI based version very minimal. It is very fun to code the UI in SwiftUI.

## Configuration details

The view is an example of listing configurations and info about configurations.

![](/images/RsyncOSX/master/swiftui/tabview.png)

## Estimation

Executing single tasks is working. This is an estimating run.

![](/images/RsyncOSX/master/swiftui/estimate.png)

## Execution

And after the estimating run, the real run. And both `synchronize` and `snapshot` run is working and the logging part.

![](/images/RsyncOSX/master/swiftui/execute.png)
