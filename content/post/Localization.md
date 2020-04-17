---
layout: post
title:  "Localization"
permalink: Localization
---
RsyncOSX and the menu app RsyncOSXsched are prepared for localization. RsyncOSX is translated to Chinese (Simplified), German, Norwegian and French. RsyncOSXsched is translated to German, Norwegian and French. Default language for both is English


RsyncOSX is localized to:
- Chinese (Simplified) -  by [StringKe](https://github.com/StringKe)
- German - by [Andre](https://github.com/andre68723)
- French - translated by [crowdin](https://crowdin.com/project/rsyncosx)
- Norwegian - by me
- English - by me and the base language of RsyncOSX

Localization is done by utilizing [Crowdin](https://crowdin.com/project/rsyncosx) to translate the xliff files which are imported into Xcode after translating. Xcode then creates the required language strings. [Crowdin is free for open source projects](https://crowdin.com/page/open-source-project-setup-request).

Volunteers are wanted for translating to other languages. Please create an issue if you have possibility to translate. Translating to new languages is mostly a proofreading exercise. [Crowdin](https://crowdin.com/project/rsyncosx) does most of the work and proofreading is last step before importing into code.

Main view in English, Chinese (Simplified), German, Norwegian and French.
![](/images/RsyncOSX/master/localization/en.png)
![](/images/RsyncOSX/master/localization/zh-Hans.png)
![](/images/RsyncOSX/master/localization/de.png)
![](/images/RsyncOSX/master/localization/nb.png)
![](/images/RsyncOSX/master/localization/fr.png)
