+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Signing and notarization"
tags = ["notarize","signed"]
categories = ["sequrity"]
description = "Some info about signing and notarizing."
lastmod = "2020-08-06"
+++
RsyncOSX is signed with my Apple ID developer certificate and [notarized](https://support.apple.com/en-us/HT202491) by Apple. This means both apps are verified and checked for not containing malicious code. It ensures the users that the apps are clean and that they are working together with Apples Gatekeeper technology. A message from Apple is issued when opening either a new or updated application the first time.

From macOS 10.15 Catalina, [notarizing is required for all software](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution).

This is the message when opening a downloaded version.

![](/images/RsyncOSX/master/notarize/verify.png)

The message is "Apple checked it for malicious software and none was detected." You can also verify the signing by utilizing xcode developer tools. If you have Xcode developer tools installed, by executing the following command you can verify the following apps:

```
xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app
Processing: /Volumes/Home/thomas/GitHub/RsyncOSX/Build/Products/Release/RsyncOSX.app
The validate action worked!

xcrun stapler validate no.blogspot.RsyncOSXsched RsyncOSXsched.app
Processing: /Volumes/Home/thomas/GitHub/RsyncOSXsched/Build/Products/Release/RsyncOSXsched.app
The validate action worked!
```
