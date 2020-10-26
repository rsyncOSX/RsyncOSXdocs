+++
author = "RsyncOSX"
date = "2020-04-23"
title =  "JSON support"
tags = ["json","config file"]
categories = ["general information"]
description = "Some info about signing and notarizing."
lastmod = "2020-10-22"
+++
**Not yet released**.

RsyncOSX supports read and write configurations and logs as [JSON](https://en.wikipedia.org/wiki/JSON) files. The user will have the option to convert existing configurations and logs from [plist](https://en.wikipedia.org/wiki/Property_list) to JSON. The JSON support is part of work to make a cross-plattform version of RsyncOSX utilizing [TypeScript](https://en.wikipedia.org/wiki/TypeScript) (and other tools).

If there will be a cross-plattform version of RsyncOSX in 2021 remains to see. It depends on how much work there is and if I am able to learn how to make apps with TypeScript and other tools.

For the moment only RsyncOSX support JSON, the menu-app does not. The menu-app will support JSON after next release again.

Before converting to JSON, in userconfig make a backup of the current configuration files. The current configurations is backed up in the catalog `$HOME/Documents/RsyncOSXcopy-timestamp`.

## Enabling JSON

To enable JSON support is a **two step** process. There are three parts in the File menu dedicated for JSON support:

- Verfiy (JSON), `⌘V`verify either converted JSON or PLIST files
- View output `⌘O`, after a verify open the output and select Logfile (select by a return in output view)
- Transform `⌘J`, enables the transform button for either JSON or PLIST

![](/images/RsyncOSX/master/json/filemenu.png)

Firs task is select the `Transform` (or just `⌘J`). The main view shows a `JSON` button (or a `PLIST` button). Selecting the button executes the transformation. The existing plist or JSON configurations are not changed.

![](/images/RsyncOSX/master/json/transform.png)

## Transforming to JSON

After transforming, the second task is to enable JSON support by selecting the `JSON` option in the user config.

![](/images/RsyncOSX/master/json/userjson.png)

## JSON enablet

RsyncOSX will automatically quit and after a restart JSON support is enablet. For new users only select the `JSON` option to enable JSON support.

![](/images/RsyncOSX/master/json/json.png)

A yellow label indicates JSON support is enablet. The JSON files are stored in:

- `./rsyncosx/macserial/configurations.json` for configurations (add profilename if profile is used)
- `./rsyncosx/macserial/schedules.json` for schedules

Example of [what the JSON files looks like, see here](https://github.com/rsyncOSX/RsyncOSX/tree/master/XCTestconfiguration/). The JSON files are a transformation of the xml (plist) files. The files are used as test of RsyncOSX after code changes.

## Returning to PLIST

You can anytime go back to plist format. Select Transform or `⌘J` and select the `PLIST` button in main view. It saves the current configurations and schedules as plist format. In userconfig disable the `JSON` support and after restart plist is enablet.
