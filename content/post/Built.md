+++
author = "Thomas Evensen"
date = "2022-05-01"
title =  "How are the apps built?"
tags = ["built"]
categories = ["general information"]
lastmod = "2022-12-29"
+++
This page is under development.

This page is for documentation of the major components of RsyncOSX and RsyncUI. But it will not document enough details to get a clear and precise understanding. Classes and structs for both apps are *focused* to keep them small and easy to understand (probably). And the name of structs, classes, variables and functions will also inform in some matter what it does (probably). 

The development of the apps has been an evolving process. Today both apps are stabel and they are in a state of maintenace. Google and the open source community has been and stil are great resources for ideas and how to solve spesific tasks. Another focus has also been to utilize functions within Swift and SwiftUI libraries. Functions exposed by the libraries are way more effective than I am able to write myself. And it is much more effective to utilize most out of the functions within the libraries.

| App      | Lines of code | Swift files |
| ----------- | ----------- |   ----------- |
| RsyncOSX   | about 160K   | 130       |
| RsyncUI   | about 170K        | 170       |

## RsyncOSX vs RsyncUI

RsyncOSX and RsyncUI shares a few of the basic components. 

| App      | Code | Paradigm |
| ----------- | ----------- |   ----------- |
| RsyncOSX   | Swift, Storyboard   | imperativ       |
| RsyncUI   | SwiftUI, Swift | declarativ  (SwiftUI)     |

RsyncOSX is a pure Swift and Storyboard based macOS application. RsyncUI is a pure SwiftUI and Swift based macOS application.  Both apps utilizes another great declarative library Combine developed by Apple. As well as JSON files for storing tasks, logrecords and user configuration. 

The major difference between the two apps is the UI part and how the UI is designed and built. 

*RsyncOSX* utilizes Storyboard, which is a tool for graphical design of views. All UI components like buttons, tables and other UI components are added and placed within the view by Xcode. After design all UI components are connected, create bindings, to Swift code. This is a manual action performed by the developer. If the developer misses to bind a UI component the app will crash with an nil pointer exception every time that view is exposed.

*RsyncUI* utilizes SwiftUI for all UI parts. All UI parts are views, which is a value type struct and not a reference type class, and they are programatically coded. A  value type cannot be changed unless utilizing a mutating function. In  SwitfUI there are special property wrappers like `@State` and `@Binding` for local and private properties and properties for transferring data between views . There are property wrapper  like `@StateObject` which are of reference type. The latter property wrapper is initialized in the view as a class of type Observeable object. And there are many other property wrappers to be used within SwiftUI. RsyncUI utilizes only a few.

Every time like a property wrapper is changed the view in a SwiftUI based app is reloaded. By reload means the view is recreated by the runtime. The model for when and how to reload is complex, but it is superfast. The cost of creating a value type vs creating a reference type is way more effective.

## Asynchronous execution

Asynchronous execution of tasks are a key component of both apps. There are two methods for asynchronous execution. One is utilizing *callback functions* or *completion handlers*, which trigger next action when task is completed. The second is utilize Swift´s `async` and `await` utilities for asynchronous execution. Utilizing `async` and `await` makes the code simpler and cleaner. The need for callback functions are reduced.  And lesser code is better code.

All code which utilizes asynchronous execution are shared between the two apps. The `Process` object is where the real work is done. Input to the `Process` are the command to execute and the parameters for the command. The `Process` object utilizes Combine for monitoring process termination and output, when needed by the apps, from the command. 

There are two versions of the process object:

- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift)
- [the async process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessAsync.swift)

The difference between those two objects are minor, the async version marks the function for execution with keyword `async`. Calling the `async` require the `await` keyword. 

- [the await keyword](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ExecuteTaskNow.swift)

## Combine

Combine makes the code easy to write and easy to read. In the Combine code for encode and write data to JSON file, the publisher requiere **macOS BigSur** and later. Combine is utilized in the following parts of RsyncOSX and likewise for RsyncUI. All code where Combine is utilized is shared between the two apps.

- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadUserConfigurationJSON.swift) user configurations from permanent store
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/TrimTwo.swift) from rsync process



