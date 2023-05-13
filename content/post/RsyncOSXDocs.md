+++
author = "Thomas Evensen"
title = "RsyncOSX - a GUI for rsync"
date = "2022-05-09"
tags = ["overview"]
categories = ["general information"]
lastmod = "2022-05-09"
+++

RsyncOSX is a pure Swift based macOS application utilizing the command line tool `rsync` for synchronizing files. It is `rsync` which executes the actual synchronize task. RsyncOSX is a GUI only ontop of `rsync`. RsyncOSX is signed and notarized by Apple. Apple has verified it for not containing malicious code and digitally signed it. 

`rsync` is a file based tool for synchronization of files.

# Before commenze use of RsyncOSX

[RsyncOSX](https://github.com/rsyncOSX/RsyncOSX/releases) is compiled for **macOS Big Sur** and later. See [the changelog](/post/changelog/) for updates. RsyncOSX is built as a Universal macOS Binary and runs natively on Apple Silicon and Intel based Mac computers.

RsyncOSX can be installed by homebrew by command `brew install --cask rsyncosx` or by download [the latest version](https://github.com/rsyncOSX/RsyncOSX/releases). If installed by homebrew the shasum is automatically verified. If downloaded from GitHub please verify the shasum.

## Remote servers, passwordless logins and local disks

RsyncOSX can synchronize your data to either remote servers on Internet and local LAN, or to local attached disks. If you only want to synchronize data to a local attached disk, connect the disk and just add the source and destination and you are ready for your first task. 

If you want to synchronize data to remote servers there are some more setup to do. If you already have enabled **passwordless login** by `ssh` you only have to add login id and servername, the source and destination and you are ready.  If you have not enabled  passwordless login there are some more actions requiered before your first task. See chapter *Remote servers* below.

## First time

The first time RsyncOSX starts it presents a link to [important](/post/important/) information. There is also info about the latest [version of rsync](/post/rsync/) to install.

{{< figure src="/images/RsyncOSX/master/start/start.png" alt="" position="center" style="border-radius: 8px;" >}}

The error in bottom of the view is only RsyncOSX complaining about not finding the default file for stored tasks. The error disappears as soon as the first task is added.

## Aborting a task

Please be aware it is an external task not controlled by RsyncOSX which executes the command line tool `rsync`. RsyncOSX is monitoring the task for progress and termination. The user can abort a task at any time. Please let the abort to finish and cleanup properly before starting a new task. It might take a few seconds. If not the apps might become unresponsive.

One of many advantages of utilizing `rsync` is that it can restart and continue the synchronize task from where it was aborted.

# Disqus

At the bottom of the page you can use Disqus to ask questions, suggest enhancments and report bugs. 

# Ready to start using RsyncOSX

## New tasks, verify and synchronize data

After [adding a task](/post/addconfigurations/), a double click on the new task will execute a simulated run or what is called a `dryrun`. Verify the output from rsync by opening the log, top left icon in sidebar of RsyncOSX, either ahead or after the simulated run. 

After adding a task you are ready to execute a [synchronize data task](/post/singletask/).

For more experienced users of rsync, select the new task and press the `Command` button. Copy and paste the `Synchronize` string into a terminal view for verification of added task. The rsync command includes the `dryrun` parameter as default within this view. 

**Always** verify, by a `dryrun`,  the result of a **new** task before executing it.

## Add parameters to rsync

Rsync has a ton of parameters. In user selected parameters you can add your own additional parameters to rsync. There is also a set of default rsync parameters.

- default [parameters](/post/rsyncparameters)
- user selected [parameters](/post/userparameters/)

## Remote servers and passwordless logins

There are two ways to setup passwordless logins to a remote server. RsyncOSX supports both. It is **strongly** advised to use ssh and ssh-keys because the traffic is encrypted and it is considered more secure.

### Encrypted protocol by ssh and ssh-keys

Using [ssh-keys](https://wiki.archlinux.org/index.php/SSH_keys) is in general considered more safe than standard password solutions (single factor authentication). Ssh-keys are based upon [public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography).

- RsyncOSX can assist you [in setting up passwordless logins](/post/ssh/)

Rsync transfer data between client and server by tunneling transfer of data in an encrypted ssh tunnel.

### Not encrypted protocol by rsync daemon

There is also possible to setup RsyncOSX utilizing a rsync daemon setup for synchronizing files to remote servers.

- this is a special setup and require [some tweaking](/post/rsyncdaemon/)

Rsync is reading a local file with password information when connecting to the server side rsync daemon. The transfer of data between client and server is not encrypted.

Snapshots is **not** possible with rsync daemon setup.

## Snapshots

[Snapshot is an effective method](/post/snapshots/) for saving previous versions of data and deleted files in case of a restore.

## Restore of files

Sometimes you need to [restore files](/post/restore/).

## User configuration

There are a few [user selected options](/post/userconfiguration/).

## RsyncOSX config files

Where does RsyncOSX [stores the config files](/post/configfiles/)?

## Compile and how is the apps built

And there is some info about how [to compile RsyncOSX](/post/compile/) and some overview of how the apps are [built](/post/built/).
