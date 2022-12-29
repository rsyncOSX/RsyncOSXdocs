+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "How are the apps built?"
tags = ["built"]
categories = ["general information"]
lastmod = "2022-12-29"
+++
RsyncOSX and RsyncUI shares a few of the basic components. RsyncOSX is a pure Swift and Storyboard based macOS application. RsyncUI is a pure SwiftUI and Swift based macOS application.  SwiftUI is a *declarative* programming paradigm vs Swift´s *imperativ* paradigm. Both apps utilizes another great declarativ library Combine developed by Apple. As well as JSON files for storing tasks, logrecords and user configuration. 

## RsyncOSX vs RsyncUI

The major difference between the two apps is the UI part and how the UI part is built. 

RsyncOSX utilizes Storyboards which is a graphical design of how the UI is compiled. All UI components within a view like buttons, tables and other UI components are added and placed within the view by Xcode. After design all UI views and components within a view are connected to Swift code. This is a manual action performed by the developer. If a UI component is not connected the app will crash with an nil pointer exception.

RsyncUI utilizes SwiftUI for all UI parts. All UI parts are views, which programatically are structs (not classes), and they are programatically coded. A view, or struct, cannot be changed unless utilizing what is called a mutating function. In  SwitfUI there are special mutable property wrappers like `@State` and `@Binding` for local and private properties and properties for transferring data between views . There are property wrapper  like `@StateObject` which are of reference type. The latter property wrapper is initialized in the view as a class of type Observeable object. And there are other property wrappers to use within SwiftUI.

## Asynchronous execution

Asynchronous execution of tasks are a key component of both apps. There are two methods for asynchronous execution. One is utilizing *callback functions* or *completion handlers*, which trigger next action when task is completed. The second is utilize Swift´s `async` and `await` utilities for asynchronous execution. Utilizing `async` and `await` makes the code simpler and cleaner. The need for callback functions are reduced.  And lesser code is better code.

There are two versions of the process object:

- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift)
- [the async process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessAsync.swift)

The difference between those two objects are minor, the async version marks the function for execution with keyword `async`. Calling the `async` require the `await` keyword. 

- [the await keyword](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ExecuteTaskNow.swift)

## Combine

Combine makes the code easy to write and easy to read. In the Combine code for encode and write data to JSON file, the publisher requiere **macOS BigSur** and later. Combine is utilized in the following parts of the app:

- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadUserConfigurationJSON.swift) user configurations from permanent store
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/TrimTwo.swift) from rsync process



