+++
author = "Thomas Evensen"
date = "2021-04-16"
title =  "Logging"
tags = ["RsyncOSX files"]
categories = ["general information"]
description = "There are a few logging options to file in RsyncOSX."
lastmod = "2020-12-13"
+++
Logging in RsyncOSX might be switched on/off in user configuration. All log records are listed in table within Logs tab. The log records are by default sorted with most recent ontop. Log records can be **filtered** by **date** by search field. Any column can be sorted by selecting the appropriate column. The sort direction, ascending or descending, is selected by direction of the arrow.

Log records can be selected for delete as well. To filter a log record select the appropriate column. As an example you might filter logs by date or month and then select all filtered log records for deleting. You are prompted to confirm a deleting of log records.

## Snap

The snap button marks logs for delete. It is only valid for snapshots. The marked logs are log records where the appropriate snapshot catalog is cleaned and deleted. Snapshots are cleand within the [snapshot tab](/post/snapshots/).

{{< image src="/images/RsyncOSX/master/logging/logs.png" alt="" position="center" style="border-radius: 8px;" >}}
