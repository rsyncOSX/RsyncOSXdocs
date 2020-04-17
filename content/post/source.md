---
layout: post
title:  "Documentation of RsyncOSX source"
permalink: Source
---
This is some documentation of the design and code of RsyncOSX. The documentation is only a brief summary of some parts of RsyncOSX. The design of RsyncOSX is based upon ideas of the [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) pattern. One of the objectives in MVC is to separate the views and models.

First will the data model and some of the methods operating on the data be documented. After that some of the high level details about how RsyncOSX is working. RsyncOSX kicks off the `rsync` utility to do the real work. The `rsync` is executed in a `Process` object.

Every time RsyncOSX [executes](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ProcessCmd.swift) a command, RsyncOSX is listening for two notifications `didTerminateNotification` and `NSFileHandleDataAvailable`. Those two notifications kicks of other functions depended upon the state of RsyncOSX.

I am also adapting most of the code to [SwiftLint](https://github.com/realm/SwiftLint) guidelines for code. Most of the classes are compliant and a few are not. The main reason for this is I discovered SwiftLint to late in development. This project commenced because I wanted to learn Swift. And the codebase from beginning until now is quite different.


# Data model

The views has no knowledge about the models or data stored about configurations, schedules and logdata. Data presented in RsyncOSX are mostly table data. Presenting table data in all views utilizes the `NSTableViewDelegate`. All data which are saved to permanent storage (`configurations`, `schedules`, `logs` and `userconfig`) are stored as xml-files ([plist](https://en.wikipedia.org/wiki/Property_list) files). RsyncOSX does not utilize the Core Data because the data about `configurations`, `schedules` and `logs` are simple and there is no need for a complex datamodel.

Data is read from permanent store and loaded when RsyncOSX either starts or if a new profile is either selected or created. The Synchronize view loads and holds the data objects during lifetime of data. There are **two** main objects which holds the data about `configurations` and `schedules` including logdata. The objects lives during lifetime of RsyncOSX or until a profile is either selected or created.

Classes in Swift are *by reference* and both the  `configurations` and `schedules` objects are created in the Synchronize view of RsyncOSX. Other objects utilizing data and methods in `configurations` and `schedules` objects are by protocol functions, getting the reference for the data objects. The references to  `configurations` and `schedules` are `weak` to avoid strong references and memory leaks.

## Configurations

The class `Configurations` (plural) holds required data, as an `Array<Configuration>`, about all tasks including all parameters for rsync and user selected parameters. All `Configuration` objects, which is a struct about one task, are stored in memory in an `Array<Configuration>` in order loaded from permanent storage. Last timestamp for execution is also stored in the `configuration` object.

- the **struct** [Configuration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) holds data about one task
- the **class** [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) holds all computed data and methods operating on tasks

Documentation of [Configurations](/Configuration).

## Scheduled tasks and log records

All log records are stored in a Schedule record. For one task it might be several schedule records depended upon type of schedule and start of scheduled task. The type of schedules are `manual`, `once`, `daily` and `monthly`. If Schedules is not used meaning only manually executed tasks, one Schedule record is created with type `manual`. All log records for this manually executed tasks are added to this record.

Documentation of [scheduled tasks and log records](/Schedule).


## Reading and writing data to permanent storage

One object takes care of reading and writing data to permanent storage. The object is also responsible to either read or write data utilizing profiles.

Documentation of [reading and writing](/Readwrite).

## Parameters to rsync

Rsync utilizes a ton of parameters. RsyncOSX let the user pass any parameter to rsync. A few rsync parameters are predefined, both mandatory and user selected. Documentation of [rsync parameters in RsyncOSX](/Parameters).

## The main view controller

Documentation of [the main viewcontroller](/Viewcontroller).
