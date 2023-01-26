+++
author = "Thomas Evensen"
date = "2022-05-01"
title =  "How are the apps built?"
tags = ["built"]
categories = ["general information"]
lastmod = "2023-01-03"
+++
*Under development.* This page is an overview of the main components of RsyncOSX and RsyncUI. The development of the apps has been an evolving process. The open source community has been and still are a great resource for ideas and how to solve spesific tasks. Both apps are today stable and in a state of maintenace. Some numbers:

| App      | Lines of code | Swift files |
| ----------- | ----------- |   ----------- |
| RsyncOSX   | about 160K   | 130       |
| RsyncUI   | about 170K        | 170       |

# Some building blocks

The following adresses some of the main building blocks of both apps and the main difference between them. The MVC design pattern is basis for both apps. 

## RsyncOSX vs RsyncUI

RsyncOSX and RsyncUI shares most of the code for *the model components*. RsyncOSX is a pure Swift and Storyboard based macOS application. RsyncUI is a pure SwiftUI and Swift based macOS application.  Both apps utilizes another great declarative library Combine developed by Apple. As well as JSON files for storing tasks, logrecords and user configuration. The main difference between the two apps is the UI and how the UI is designed and built. 


| App      | Code | Paradigm |
| ----------- | ----------- |   ----------- |
| RsyncOSX   | Swift, Storyboard   | imperativ (Swift)      |
| RsyncUI   | SwiftUI, Swift | declarativ  (SwiftUI)     |

### RsyncOSX and Storyboard

*RsyncOSX* utilizes *Storyboard*, which is a tool for graphical design of views. UI components like buttons, tables and other UI components are added and placed within the view by the developer utilizing Xcode. After design all UI components are connected by creating bindings to Swift code. The developer manually adds a reference to the Swift source code for every view  within the Storyboard. If the developer misses to bind a UI component, the app will crash with an nil pointer exception every time that view is exposed.

Storyboard for the tab views:
{{< image src="/images/Xcode/storyboard1.png" alt="" position="center" style="border-radius: 8px;" >}}
Storyboard for the sheetviews:
{{< image src="/images/Xcode/storyboard2.png" alt="" position="center" style="border-radius: 8px;" >}}

### RsyncUI and SwiftUI

*RsyncUI* utilizes *SwiftUI* for the UI. UI components are views, which is a value type `struct` and not a reference type `class`. UI components are added to RsyncUI by code. Example of a view is the [Details view](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Views/Detailsview/DetailsView.swift) selecting the `DryRun` button.

The details view:
{{< image src="/images/Xcode/detailsview.png" alt="" position="center" style="border-radius: 8px;" >}}

 A property within a value type can only be modified by a `mutating func`. In  SwitfUI there are special property wrappers like `@State` and `@Binding` for local and private properties and properties for transferring data between views . These property wrappers enables to modify a property within a SwiftUI view. There are property wrapper  like `@StateObject` which are of reference type. The latter property wrapper is initialized in the view as a class of type Observeable object. And there are many other property wrappers to be used within SwiftUI. RsyncUI utilizes only a few.

Every time like a property wrapper is changed the view in a SwiftUI based app is recreated by the runtime. The internal model for creating views is a kind of complex and it is superfast. The cost of creating a value type vs a reference type is way more effective.

## Asynchronous execution - boths apps

Asynchronous execution of tasks are key components of both apps. Every time a `rsync` synchronize or restore task is executed the termination of the task is not known ahead.  When the termination signal is observed some actions are requiered. Some actions are like stopping a progressview, send a message about task is completed, do some logging and execute next synchronize task.

There are two methods for asynchronous execution. One is utilizing *callback functions* or *completion handlers*, which trigger next action when task is completed. The second is utilize Swift´s `async` and `await` utilities for asynchronous execution. Utilizing `async` and `await` makes the code simpler and cleaner. The need for *completion handlers* are reduced.  And lesser code is better code.

All code which utilizes asynchronous execution are shared between the two apps. The `Process` object is where the real work is done. Input to the `Process` are the command to execute and the parameters for the command. The `Process` object utilizes Combine for monitoring process termination and output, when needed by the apps, from the command.  There are two versions of the process object:

- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift)
- [the async process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessAsync.swift)

The difference between those two objects are minor, the async version marks the function for execution with keyword `async`. Calling the `async` require the `await` keyword. 

- [the await keyword](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ExecuteTaskNow.swift)

## Combine  - boths apps

Combine, a declarative library by Apple, makes the code easy to write and easy to read. In the Combine code for encode and write data to JSON file, the publisher requiere **macOS BigSur** and later. Combine is utilized in the following parts of RsyncOSX and likewise for RsyncUI.

- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadUserConfigurationJSON.swift) user configurations from permanent store
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadConfigurationJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteConfigurationJSON.swift) configurations
- [read](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadScheduleJSON.swift) and [write](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/WriteScheduleJSON.swift) schedules and logs
- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift), executing tasks
- preparing [the output](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/TrimTwo.swift) from rsync process

# How to start the apps

There are different ways of starting a Storyboard based app vs a SwiftUI based app.

## Start of RsyncUI

The start of RsyncUI conforms to the [App protocol](https://developer.apple.com/documentation/SwiftUI/App). There is only one entrance point `@main` in [RsyncUI](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Main/RsyncUIApp.swift). The `@main` initializes the app, setup of the menubar and open the [navigation bar](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Main/RsyncUIView.swift) which is the main user start for the app.

## Start of RSyncOSX

The start of RsyncOSX starts with the attribute `@NSApplicationMain` which kicks off everything. Within the Storyboard the entrypoint is marked and the view is binded with [MainWindowsController.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/MainWindowsController.swift). The [Toolbar](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Toolbar.swift) is programatically constructed which makes it more easy to change vs designing it the Storyboard. But all the details how this actually work is beyond me, but it works.



