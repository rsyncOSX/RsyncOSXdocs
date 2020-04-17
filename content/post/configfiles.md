---
layout: post
title:  "RsyncOSX config files"
permalink: configfiles
---

RsyncOSX stores its configurations, schedules, log records and user configuration as [property list files](https://en.wikipedia.org/wiki/Property_list). There are three kinds of files and all are stored in the Documents/Rsync catalog. RsyncOSX evaluates the computer mac serial number at startup and all files are stored in `Documents/Rsync/macserialnumber`

### Configuration files

Default profile stores all configurations in:

- `Documents/Rsync/macserialnumber/configRsync.plist`

If profile is utilized:

- `Documents/Rsync/macserialnumber/profile/configRsync.plist`

where profile is a sub catalog.

### Schedules and log records

Default profile stores all Schedules and log records in:

- `Documents/Rsync/macserialnumber/scheduleRsync.plist`

If profile is utilized:

- `Documents/Rsync/macserialnumber/profile/scheduleRsync.plist`

### User configurations

The user configurations is stored in:

- `Documents/Rsync/macserialnumber/config.plist`.

The user settings applies to all profiles.
