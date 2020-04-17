---
layout: post
title:  "Configurations (tasks)"
permalink: Configuration
---
The configurations are read from the permanent storage and kept in memory until a new profile is loaded or RsyncOSX quits. Each record (one task) are read from permanent storage as a `NSDictionary` item, copied to a `Configuration` and loaded into an `Array<Configuration>`.

- the **struct** [Configuration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) holds data about one task
- the **class** [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) holds all computed data and methods operating on tasks
  - the object is also responsible for initiate reading data from permanent store when the object is created
  - the object is also responsible for initiate a write operation after any change in configurations

Every time configurations are read from permanent store, the rsync arguments are [computed](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/RsyncParameters.swift) and the result is stored in memory only by the struct [ArgumentsOneConfiguration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/ArgumentsOneConfiguration.swift). There are several arguments which are computed during startup, arguments for `--dry-run`, real run and arguments for presentation on screen. Each configuration is allocated a uniq computed nonsense key `hiddenID = Int`.

The class [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) creates an `Array<NSMutableDictionary>` which holds all data about [Configuration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) and computed values of rsync arguments. Computed values are **not** saved to permanent storage. They are computed either when RsyncOSX starts or when a new profile is loaded. Any changes (change, delete, new operations) causes a read from permanent store.

### Changes to configurations

Changes to configurations (change, delete, new, parameters to rsync) is a **three** step operation:
- any change, delete, new or parameters to rsync operations on configurations are updated in memory (to the `Array<Configuration>`)
  - [Configuration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configuration.swift) is a struct holding all attributes for one task
- any change, delete or add operation causes a write operation from memory to permanent store of all configurations
  - the `Array<Configuration>` are transformed into an `Array<NSDictionary>` in the class [PersistentStorageConfiguration.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/PersistentStorageConfiguration.swift) before a write operation is executed
- the object [Configurations.swift](https://github.com/rsyncOSX/RsyncOSX/blob/master/RsyncOSX/Configurations.swift) is created, a read operation is initiated and new values are computed
There is no need for partly updates and it secures a 100% correct and updated configuration in memory at all time.
