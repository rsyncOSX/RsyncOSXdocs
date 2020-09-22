+++
author = "RsyncOSX"
date = "2020-04-16"
title =  "RsyncOSX config files"
tags = ["RsyncOSX files"]
categories = ["config files"]
description = "Where does RsyncOSX stores the various configuration files."
+++
RsyncOSX stores its configurations, schedules, log records and user configuration as [property list files](https://en.wikipedia.org/wiki/Property_list). There are three kinds of configuration files.

Existing users can choose to move configuration files to new localization. In the About the used path for configuration files is shown.

## Version 6.4.5 and future releases

From version 6.4.5 RsyncOSX all configuration files are store in `$HOME/.rsyncosx/macserialnumber`. RsyncOSX evaluates the computer mac serial number at startup.

## Version 6.4.2 and previous versions

In version 6.4.2 all configuration files are stored in `Documents/Rsync/macserialnumber`

## Configuration files

Default profile stores all configurations in:
```
$HOME/.rsyncosx/macserialnumber/configRsync.plist
```
If profile is utilized:
```
$HOME/.rsyncosx/macserialnumber/profile/configRsync.plist
```
where `profile` is a sub catalog.

## Schedules and log records

Default profile stores all Schedules and log records in:
```
$HOME/.rsyncosx/macserialnumber/macserialnumber/scheduleRsync.plist
```
If profile is utilized:
```
$HOME/.rsyncosx/macserialnumber/profile/scheduleRsync.plist
```
## User configurations

The user configurations is stored in:
```
$HOME/.rsyncosx/macserialnumber/config.plist
```
The user settings applies to all profiles.
