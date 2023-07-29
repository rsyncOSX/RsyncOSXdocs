+++
author = "Thomas Evensen"
date = "2022-05-01"
title =  "How are the apps built?"
tags = ["built"]
categories = ["general information"]
lastmod = "2023-01-03"
+++
*Under development.* This page is an overview of the main components of RsyncOSX and RsyncUI. The development of the apps has been an evolving process. The open source community has been and still are a great resource for ideas and how to solve specific tasks. Both apps today are stable and in a state of maintenace. 

Some numbers:

| App      | Lines of code | Swift files | Version 1.0 |
| ----------- | ----------- |   ----------- | -------- |
| RsyncUI   | about 14K     | about 170       | 6 May 2021 |
| RsyncOSX   | about 11K   | about 120      | 14 March 2016 |	


Which application to use? Both applications does the same job. They read and update the same files for tasks and logs which mean you can use both apps, but not at the same time due to locking of files. According to Apple SwiftUI is the future. RsyncUI is built by utilizing SwiftUI and by every new release of macOS, Swift and SwiftUI there are new features supporting the new release of macOS. This is also true for Swift 5.9, Xcode 15 and macOS Sonoma (macOS 14). By Swift 5.9 the new `Observable` macro replace the  `@StateObject` propertywrapper. This is a *breaking* change and there will be two releases for RsyncUI when macOS Sonoma is public. 

## A few words about the code

Even if I am an educated IT person most of my professional work has been as an IT-manager and not a developer. Most of my coding experience is in private projects such as RsyncOSX and RsyncUI. Google is and has been a great resource for research and advice on how to solve specific problems. Reading other developers' code and discussing is always valuable input for my code. The *MVC pattern* and *single source of truth* are important patterns for both apps. I have also tried to use all Apple Frameworks utilizing most required built-in functions like I **don't write** my own sorting or filter algorithms. And even if there are many lines of code in both apps I have tried to write as little code as possible.  So if you are looking at my code keep this in mind and my code is *only one* of *probably many ways* to solve a problem.  

## RsyncOSX vs RsyncUI

RsyncUI and RsyncOSX shares most of *the model components*.  There are though some model components within RsyncUI which are like an interface between the *shared* model and RsyncUI views. The main differences between the two apps are the user interface (UI) and how the UI is built. RsyncUI is deveoped by utilizing **SwiftUI** and Swift.  RsyncOSX is developed by utilizing **Storyboards** and Swift.  Both apps utilizes another great **declarative** library, Combine, developed by Apple and JSON files for storing tasks, logrecords and user configuration. RsyncUI is now the primary application of the two even if RsyncOSX has more users. 

| App      | Code | Paradigm |
| ----------- | ----------- |   ----------- |
| RsyncUI   | SwiftUI, Swift | declarativ  |
| RsyncOSX   | Storyboard, Swift  | imperativ |

SwiftUI is the latest declarative framework developed by Apple for views, controls, and layout structures for user interface. 

### RsyncUI and SwiftUI

*RsyncUI* utilizes *SwiftUI* for the UI. UI components are views, which is a value type `struct` and not a reference type `class`. UI components are added to RsyncUI by code.  Every time a property within a SwiftUI view is changed the view is recreated by the runtime. The internal model for creating views is a kind of complex and it is superfast. The cost of creating a value type vs a reference type is way more effective.  In SwitfUI there are special propertywrappers like `@State` and `@Binding` for local and private properties and properties for transferring data between views . These propertywrappers enables to modify a property within a SwiftUI view. 

#### macOS Sonoma

On macOS Sonoma and by Swift 5.9 there is a new `Observable` macro  which replaces `@StateObject`. The new macro makes it even more easy to write code for the model part which automatically communicate updates of data to the view for updates.

#### macOS Monterey and macOS Ventura
 
The propertywrapper  `@StateObject` is used in combination with Combine for the model part for automatically communicate updates of data to the view for updates.

### RsyncOSX and Storyboard

*RsyncOSX* utilizes *Storyboard*, which is a tool for graphical design of views. UI components like buttons, tables and other UI components are added and placed within the view by the developer utilizing Xcode. After design all UI components are connected by creating bindings to Swift code. The developer manually adds a reference to the Swift source code for every view  within the Storyboard. If the developer misses to bind a UI component, the app will crash with an nil pointer exception every time that view is exposed.

Storyboard for the tab views:
{{< figure src="/images/Xcode/storyboard1.png" alt="" position="center" style="border-radius: 8px;" >}}
Storyboard for the sheetviews:
{{< figure src="/images/Xcode/storyboard2.png" alt="" position="center" style="border-radius: 8px;" >}}


## Asynchronous execution - boths apps

Asynchronous execution of tasks are key components of both apps. Every time a `rsync` synchronize and restore task is executed the termination of the task is not known ahead.  When the *termination signal* is observed some actions are required. Some actions are like stopping a progressview, send a message about task is completed, do some logging and execute next synchronize task.

There are two methods for asynchronous execution. One is utilizing *callback functions* or *completion handlers*, which trigger next action when task is completed. The second is utilize Swift´s `async` and `await` utilities for asynchronous execution. Utilizing `async` and `await` makes the code simpler and cleaner. The need for *completion handlers* are reduced.  And lesser code is better code.

Swift concurrency is a seperate and huge topic to discuss. I am not in a position to discuss it. There are structured and unstructered concurrency in Swift. There are no concurrency within the applications. There are only one asynchronous execution at any time except for concurrency within the Swift and SwiftUI libraries such as GUI updates. 

All code which utilizes asynchronous execution are shared between the two apps. The `Process` object is where the real work is done. Input to the `Process` are the command to execute and the parameters for the command. The `Process` object utilizes Combine for monitoring *process termination* and output, when needed by the apps, from the command.  There are two versions of the process object:

- [the process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcess.swift)
- [the async process object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncProcessAsync.swift)

The difference between those two objects are minor, the async version marks the function for execution with keyword `async`. Calling the `async` require the `await` keyword. 

- [the await keyword](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ExecuteTaskNow.swift)

## Combine  - boths apps

Combine, a declarative library by Apple, makes the code easy to write and easy to read. In the Combine code for encode and write data to JSON file, the publisher require **macOS BigSur** and later. Combine is utilized in the following parts of RsyncOSX and likewise for RsyncUI.

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

The start of RsyncOSX starts with the attribute `@NSApplicationMain` which kicks off everything. Within the Storyboard the entry point is marked and the view is binded with [MainWindowsController.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/MainWindowsController.swift). The [Toolbar](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Toolbar.swift) is programmatically constructed which makes it more easy to change vs designing it the Storyboard. But all the details how this actually work is beyond me, but it works.

# The model

The model is not equal for the apps. The concept of model is the same, but there are some differences due to the fact that SwiftUI views are value type (structs) and not reference type (class) as for Storyboard and Swift. The model is also responsible for informing the views when there are changes to the model. But both apps share the basic functions like read and write data from store, functions for updating the model and so on. 

The memory footprint about tasks is minimal. Data for tasks are kept in memory for both apps during the lifetime of the apps. The memory footprint for logs will grow over time as new logs are created and stored. But logs are only  read from store when viewing logs or updates. When data about logs is not used, the data is automatically released from memory to keep the memory as low as possible.

## Model for RsyncUI

### macOS Sonoma

For macOS Sonoma the new `Observable` macro introduces a few changes to the code. 

Data for tasks are read from store and made avaliable for all the views by an Environment property. The [RsyncUIApp](https://github.com/rsyncOSX/RsyncUI/blob/version-1.7.0-macos-sonoma/RsyncUI/Main/RsyncUIApp.swift) is the main entrance point for RsyncUI. After the app is initialized and started it opens the [main navigation view](https://github.com/rsyncOSX/RsyncUI/blob/version-1.7.0-macos-sonoma/RsyncUI/Main/RsyncUIView.swift) and read tasks for the default profile or other profile when selected.  Data about [tasks](https://github.com/rsyncOSX/RsyncUI/blob/version-1.7.0-macos-sonoma/RsyncUI/Model/Data/RsyncUIconfigurations.swift) is made avaliable for all views by the `.environment` property. 

### macOS Monterey and macOS Ventura

Data for tasks are read from store and made avaliable for all the views by an Environment property. The [RsyncUIApp](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Main/RsyncUIApp.swift) is the main entrance point. After the app is initialized and started it opens the [main navigation view](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Main/RsyncUIView.swift) and read tasks for the default profile or other profile when selected.  Data about [tasks](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Model/Data/RsyncUIconfigurations.swift) is made avaliable for all views by the `.environmentObject` property. 

All synchronize tasks are executed asynchron.  [The process object](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Model/Process/Main/Async/RsyncProcessAsync.swift), which is responsible for executing the external rsync tasks, is listening for termination of the external process. Here is an [example of one class](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Model/Execution/ExecuteMultipleTasks/ExecuteMultipleTasks.swift) which does the real update on data is created within [this SwiftUI view](https://github.com/rsyncOSX/RsyncUI/blob/main/RsyncUI/Views/Tasks/ExecuteEstimatedTasksView.swift). 

A `StateObject` which is created when a SwiftUI view is created, is updated as progress of task. The update causes the `StateObject` to publish a change message which again trigger an action like all tasks are completed, saved to store and a new of data from store is requiered.
