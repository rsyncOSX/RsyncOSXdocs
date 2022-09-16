+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Signing and notarization"
tags = ["notarize","signing"]
categories = ["general information"]
lastmod = "2020-08-06"
+++
RsyncOSX is signed with my Apple ID developer certificate and [notarized](https://support.apple.com/en-us/HT202491) by Apple. This means that the app is verified and checked for not containing malicious code and it will work with Apples Gatekeeper technology. From macOS 10.15 Catalina, [notarizing is required for all software](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution).

The message is "Apple checked it for malicious software and none was detected." You can also verify the signing by utilizing xcode developer tools. If you have Xcode developer tools installed, by executing the following command you can verify RsyncOSX:

`xcrun stapler validate no.blogspot.RsyncOSX RsyncOSX.app`
