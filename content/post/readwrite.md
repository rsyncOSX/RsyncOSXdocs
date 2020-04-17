---
layout: post
title:  "Reading and writing data to permanent storage"
permalink: Readwrite
---
The object [ReadWriteDictionary.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ReadWriteDictionary.swift) reads and writes to permanent storage. All data (configurations, schedules and log records, user config) is read from permanent storage utilizing the [NSDictionary](https://developer.apple.com/documentation/foundation/nsdictionary) foundation class.

RsyncOSX configuration file, scheduled tasks which also includes log records and user configuration are plain XML-files ([property list files](https://en.wikipedia.org/wiki/Property_list)). Files are saved in:

- `~/Documents/Rsync/MacID/configRsync.plist` - configurations
  - `~/` is user home directory
  - `MacID` is the Mac serial number and is automatically set by RsyncOSX
- `~/Documents/Rsync/MacID/scheduleRsync.plist` - scheduled tasks including log records
- `~/Documents/Rsync/MacID/config.plist` - user config

If _profile_ is used:

- `~/Documents/Rsync/MacID/profile/configRsync.plist`
- `~/Documents/Rsync/MacID/profile/scheduleRsync.plist`
  - `profile` is the profile name
- `~/Documents/Rsync/MacID/config.plist` - user config
