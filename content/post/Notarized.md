---
layout: post
title:  "Signing and notarize the apps"
permalink: Notarized
---
 RsyncOSX and RcloneOSX are signed with my Apple ID developer certificate and [notarized](https://support.apple.com/en-us/HT202491) by Apple. This means both apps are verified and checked for not containing malicious code. It ensures the users that the apps are clean and that they are working together with Apples Gatekeeper technology. A message from Apple is issued when opening either a new or updated application the first time.

 From macOS 10.15 Catalina, [notarizing is required for all software](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution).

 The following apps are signed and notarized:

 - RsyncOSX
 - RsyncOSXsched
 - RcloneOSX

 Important: from macOS 10.15 Catalina, notarization is required by default for all software. RsyncOSX is signed and notarized and a new signed and notarized release will be available shortly after release of macOS 10.15.

## RsyncOSX

This is the message when opening a downloaded version.

![](/images/RsyncOSX/master/notarize/verifyRsyncOSX.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  The english version of it is: "Apple checked it for malicious software and none was detected."

If you have Xcode developer tools installed executing the following command `xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app` will verify RsyncOSX.
```
xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app
Processing: /Volumes/Home/thomas/GitHub/RsyncOSX/Build/Products/Release/RsyncOSX.app
The validate action worked!
```
## RsyncOSXsched (the menu app)

This is the message when opening a downloaded version.

![](/images/RsyncOSX/master/notarize/verifyRsyncOSXsched.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  The english version of it is: "Apple checked it for malicious software and none was detected."

If you have Xcode developer tools installed executing the following command `xcrun stapler validate no.blogspot.RsyncOSXsched RsyncOSXsched.app` will verify the RsyncOSX.app.
```
xcrun stapler validate no.blogspot.RsyncOSXsched RsyncOSXsched.app
Processing: /Volumes/Home/thomas/GitHub/RsyncOSXsched/Build/Products/Release/RsyncOSXsched.app
The validate action worked!
```

## RcloneOSX

This is the message when opening a downloaded version.

![](/images/RsyncOSX/master/notarize/verifyRcloneOSX.png)

The message is in Norwegian: "Apple har sjekket programmet uten å finne ondsinnet programvare."  The english version of it is: "Apple checked it for malicious software and none was detected."

If you have Xcode developer tools installed executing the following command `xcrun stapler validate no.blogspot.rcloneosx rcloneosx.app` will verify the the rcloneosx.app.
```
xcrun stapler validate no.blogspot.rcloneosx rcloneosx.app
Processing: /Volumes/Home/thomas/GitHub/RcloneOSX/Build/Products/Release/rcloneosx.app
The validate action worked!
```
