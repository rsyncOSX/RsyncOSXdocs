---
type: post
date: 2020-04-16T09:34:29+02:00
title:  "Localization"
---
RsyncOSX and the menu app RsyncOSXsched are prepared for localization.

RsyncOSX is translated to Chinese (Simplified), German, Norwegian, French and Italian.

RsyncOSXsched is translated to German, Norwegian, French and Italian.

Default language for both is English


RsyncOSX is localized to:
- Chinese (Simplified) -  by [StringKe](https://github.com/StringKe)
- German - by [Andre](https://github.com/andre68723)
- French - translated by [crowdin](https://crowdin.com/project/rsyncosx)
- Norwegian - by me
- Italian - by [Stefano Steve Cutelle'](https://github.com/stefanocutelle)
- English - the base language of RsyncOSX

Localization is done by utilizing [Crowdin](https://crowdin.com/project/rsyncosx) to translate the xliff files which are imported into Xcode after translating. Xcode then creates the required language strings. [Crowdin is free for open source projects](https://crowdin.com/page/open-source-project-setup-request).

Volunteers are wanted for translating to other languages. Please create an issue if you have possibility to translate. Translating to new languages is mostly a proofreading exercise. [Crowdin](https://crowdin.com/project/rsyncosx) does most of the work and proofreading is last step before importing into code.
