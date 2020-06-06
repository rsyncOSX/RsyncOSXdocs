+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "Parameters"
tags = ["parameters"]
categories = ["source code"]
description = "There are a few logging options to file in RsyncOSX."
+++
RsyncOSX utilizes the object [RsyncParameters.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncParameters.swift) to analyze and set whatever parameters to rsync the user sets. There are no check if parameters set for rsync is correct or not. If the user enters bad or wrong parameters, RsyncOSX passes bad parameters to rsync.

Predefined parameters to rsync are displayed setting the corresponding parameter in dropdown menus (comboboxes). If option user is selected in dropdown menus, RsyncOSX saves and passes whatever the user sets to rsync when task is executed.
