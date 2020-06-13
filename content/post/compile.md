+++
author = "RsyncOSX"
date = "2020-04-17"
title =  "How to compile RsyncOSX"
tags = ["compile"]
categories = ["source code"]
description = "If you pull RsyncOSX from GitHub you can easy compile your own version."
+++
## Before compiling

RsyncOSX is only depended upon Cocoa and  Foundation classes which are standard Swift libraries.

There are two ways to compile, either in Xcode or utilize `make` from commandline in RsyncOSX catalog. To use make require Xcode command line utilities to be installed. Execute the following command and follow the instructions.

`xcode-select --install`

## Remove signing credentials or replace

To compile you have to either remove signing or replace signing credentials. To remove or replace select Target RsyncOSX and tab "Signing and Capabilities". The first view is my signing credentials.

![](/images/RsyncOSX/master/compile/signing.png)

To remove select "Team: none" and "Signing Certificates: Sign to Run Locally".

![](/images/RsyncOSX/master/compile/nonsigning.png)

## Compile scripts

There are two utilities used, [SwiftLint](https://github.com/realm/SwiftLint) and [SwiftFormat](https://github.com/nicklockwood/SwiftFormat). Both can be removed, select tab "Build Phases" and delete the lines. Or you can use [homebrew](https://brew.sh/index_nb) to install both utilities.

![](/images/RsyncOSX/master/compile/scripts.png)

Remove the build scripts.

![](/images/RsyncOSX/master/compile/nonscripts.png)

## Ready to Compile

Either execute RsyncOSX directly in Xcode or utilize make. Go to the catalog top RsyncOSX and execute the following command.

`make clean & make`

After the compiling is completed the RsyncOSX.app is build and saved in:

`RsyncOSX/Build/Products/Release/RsyncOSX.app`
