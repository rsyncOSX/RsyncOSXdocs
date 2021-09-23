+++
author = "Thomas Evensen"
date = "2021-04-17"
title =  "How to compile RsyncOSX"
tags = ["compile"]
categories = ["source code"]
description = "If you pull RsyncOSX from GitHub you can easy compile your own version."
+++
RsyncOSX is only depended upon Cocoa and  Foundation classes which are standard Swift libraries. There are two ways to compile, either in Xcode or utilize `make` from command line in RsyncOSX catalog. To use make require Xcode command line utilities to be installed. Execute the following command and follow the instructions.
```bash
xcode-select --install
```
## Remove signing credentials or replace

To compile you have to either remove signing or replace signing credentials. To remove or replace select Target RsyncOSX and tab "Signing and Capabilities". The first view is my signing credentials.

![](/images/RsyncOSX/master/compile/signing.png)

To remove select "Team: none" and "Signing Certificates: Sign to Run Locally".

![](/images/RsyncOSX/master/compile/nonsigning.png)

## Compile scripts

There are two utilities used, [SwiftLint](https://github.com/realm/SwiftLint) and [SwiftFormat](https://github.com/nicklockwood/SwiftFormat). Both can be removed, select tab "Build Phases" and delete the lines. Or you can use [Homebrew](https://brew.sh/index_nb) to install both utilities.

![](/images/RsyncOSX/master/compile/scripts.png)

Remove the build scripts.

![](/images/RsyncOSX/master/compile/nonscripts.png)

## Ready to Compile

Either execute RsyncOSX directly in Xcode or utilize make. Go to the catalog top RsyncOSX and execute the following command.

```bash
make clean & make
```

After the compiling is completed the RsyncOSX.app is build and saved in:
```bash
RsyncOSX/Build/Products/Release/RsyncOSX.app
```
## Tools used

The following tools are used in development:

- Xcode (the main tool)
- make to compile new versions in terminal
- [create-dmg](https://github.com/sindresorhus/create-dmg) to create new releases
- [periphery](https://github.com/peripheryapp/periphery) to identify unused code
- [SwiftLint](https://github.com/realm/SwiftLint) to enforce Swift style and conventions
- [SwiftFormat](https://github.com/nicklockwood/SwiftFormat) for reformatting Swift code

All the above, except Xcode are installed by using [Homebrew](https://brew.sh/).
