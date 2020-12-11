+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "JSON support"
tags = ["json","config file"]
categories = ["general information"]
description = "Some info about signing and notarizing."
lastmod = "2020-12-11"
+++
RsyncOSX supports read and write configurations and logs as [JSON](https://en.wikipedia.org/wiki/JSON) files. The user will have the option to convert existing configurations and logs from [plist](https://en.wikipedia.org/wiki/Property_list) to JSON. Before converting to JSON, [in user configuration](/post/userconfiguration/), make a backup of the current configuration files. The current configurations is backed up in the catalog `$Home/Documents/RsyncOSXcopy-$date-suffix`.

## Enabling JSON

To enable JSON support is a **two step** process. There are three parts in the File menu dedicated for JSON support:

- Verfiy (JSON) (shortcut `⌃⌘V`) - verify either converted JSON or PLIST files
- View output (shortcut `⌘O`) -  after a verify open the output and select Logfile
- Transform (shortcut `⌘J`) - enables the transform button for either JSON or PLIST

![](/images/RsyncOSX/master/json/filemenu.png)

Firs task is select the `Transform` (or shortcut `⌘J`). The main view shows a `JSON` button (or a `PLIST` button). Selecting the button executes the transformation. The existing plist or JSON configurations are not changed.

- `JSON` button if RsyncOSX is reading PLIST files
- `PLIST` button if RsyncOSX is reading JSON files

## Transforming to JSON

After transforming, the second task is to enable JSON support by selecting the `JSON` option [in user configuration](/post/userconfiguration/)

## JSON enablet

RsyncOSX will automatically quit and after a restart JSON support is enablet. For new users only select the `JSON` option to enable JSON support.

![](/images/RsyncOSX/master/json/json.png)

A yellow label indicates JSON support is enablet. The JSON files are stored in, add profilename if profile is used:

- `./rsyncosx/macserial/configurations.json` for configurations
- `./rsyncosx/macserial/schedules.json` for schedules

Example of [what the JSON files looks like, see here](https://github.com/rsyncOSX/RsyncOSX/tree/master/XCTestconfiguration/). The JSON files are a transformation of the xml (plist) files. The files are used as test of RsyncOSX after code changes.

## Returning to PLIST

You can anytime go back to plist format. Select Transform or `⌘J` and select the `PLIST` button in main view. It saves the current configurations and schedules as plist format. In userconfig disable the `JSON` support and after restart plist is enablet.
