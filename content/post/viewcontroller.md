---
layout: post
title:  "The main viewcontroller"
permalink: Viewcontroller
---
The [main viewcontroller](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ViewControllerMain.swift) contains no logic at all. The only task for the main viewcontroller is to act on whatever the user choose of action. E.g. if the user choose to double click on a row to activate a single task (two step - estimate and execute), the main viewcontroller only create and holds a reference to a [Singletask object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SingleTask.swift).

Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ProcessCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

The [Singletask object](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/SingleTask.swift) is, after the `ProcessCmd.swift` is kicked off and executes the rsync command, activated again by either a `processTermination` or `fileHandler` function call.

All actions which are triggered from the main view (or any other view) is handled by separate task objects. The main viewcontroller is only responsible for creating objects, keep reference to the objects and close sheet views.
