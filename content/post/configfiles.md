+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "RsyncOSX config files"
tags = ["config files"]
categories = ["general information"]
description = "Where does RsyncOSX stores the various configuration files."
lastmod = "2020-10-23"
+++
RsyncOSX stores its configurations, schedules and log records and user configurations as [JSON](https://en.wikipedia.org/wiki/JSON) files. The storage of those files is:

`$HOME/.rsyncosx/macserialnumber`

In the `About` the used path for configuration files is shown. RsyncOSX evaluates the computer mac serial number at startup.

## Configuration files

`$HOME/.rsyncosx/macserialnumber/configurations.json`
If profile is utilized:

`$HOME/.rsyncosx/macserialnumber/profile/configurations.json`

## Schedules and log records

`$HOME/.rsyncosx/macserialnumber/schedules.json`

If profile is utilized:

`$HOME/.rsyncosx/macserialnumber/profile/schedules.json`

## User configurations

The [user configurations](/post/userconfiguration/) is stored as:

`$HOME/.rsyncosx/macserialnumber/rsyncosxconfig.json`

The user settings applies to all profiles.
