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

## Enabling JSON

To enable JSON support is a two step process. First task is to backup existing configurations and enable the transform function. Select the button `Transform` and close the view. After closing the user config, the main view shows a `JSON` button. After transforming, the second task is to enable JSON support by selecting the `JSON` option. RsyncOSX will automatically quit and after a restart JSON support is enablet.

Before transforming to JSON format, the current configurations is backed up in the catalog `$HOME/Documents/RsyncOSXcopy-timestamp`.

For new users only select the `JSON` option to enable JSON support.

![](/images/RsyncOSX/master/json/userjson.png)

## Transforming to JSON

After selecting `Transform` in user config, a `JSON` button is enablet. Selecting the button executes the transformation. The existing plist configurations are not changed.

![](/images/RsyncOSX/master/json/transform.png)

## JSON enablet

After transforming existing configurations, select the `JSON` option in the user config. RsyncOSX will automatically quit and after a restart, RsyncOSX reads the newly transformed JSON config files.

A yellow label indicates JSON support is enablet. The JSON files are stored in:

- `./rsyncosx/macserial/configurations.json` for configurations (add profilename if profile is used)
- `./rsyncosx/macserial/schedules.json` for schedules

Example of [what the JSON files looks like, see here](https://github.com/rsyncOSX/RsyncOSX/tree/master/XCTestconfiguration/). The JSON files are a transformation of the xml (plist) files. The files are used as test of RsyncOSX after code changes.

![](/images/RsyncOSX/master/json/json.png)

## Returning to PLIST

You can anytime go back to plist format. In userconfig select the button `Transform`, close view and select the `PLIST` button. It saves the current configurations and schedules as plist format. In userconfig disable the `JSON` support and after restart plist is enablet.
