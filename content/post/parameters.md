+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Parameters"
tags = ["parameters"]
categories = ["rsync"]
+++
RsyncOSX utilizes the object [RsyncParameters.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncParameters.swift) to analyze and set whatever parameters to rsync the user sets. There are no check of parameters set for rsync is correct. If the user enters bad parameters RsyncOSX passes bad parameters to rsync.

Predefined parameters to rsync are displayed setting the corresponding parameter in dropdown menus (comboboxes). If option user is selected in dropdown menus, RsyncOSX saves and passes whatever the user sets to rsync when task is executed.
