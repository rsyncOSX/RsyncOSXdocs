+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "RsyncOSX config files"
tags = ["config files"]
categories = ["general information"]
lastmod = "2020-10-23"
+++
RsyncOSX read and store configurations, log records and user settings as [JSON](https://en.wikipedia.org/wiki/JSON) files. The location of files is: `$HOME/.rsyncosx/macserialnumber`. RsyncOSX evaluates the computer mac serial number at startup. 

## Configuration files

`$HOME/.rsyncosx/macserialnumber/configurations.json`

If profile is utilized:

`$HOME/.rsyncosx/macserialnumber/profile/configurations.json`

## Log records

`$HOME/.rsyncosx/macserialnumber/schedules.json`

If profile is utilized:

`$HOME/.rsyncosx/macserialnumber/profile/schedules.json`

## User settings

The [user settings](/post/userconfiguration/) are stored as:

`$HOME/.rsyncosx/macserialnumber/rsyncosxconfig.json`

The user settings applies to all profiles.
