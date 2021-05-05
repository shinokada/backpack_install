# backpack_install for MacOS/Linux

## Overview

This script makes it easy to install all Backpack for Laravel modules:
BackupManager, LogManager, Settings, PageManager, PermissionManager, MenuCrud, and NewsCrud.

Tested on MacOS and it should work on Linux.

## Requirement

- You must have Laravel installed and connected to a database. No data in the database.
- sed

## Usage

Download or clone this repo.

```terminal
./backpack_install [ -a | -all ] [ -d /path/to/dir ]
    -d              path/to/project
    -a | --all      This will install all modules.
    -v | --version  Script version.
    -h | --help     Show help.
```

## Examples

```terminal
# cd to backpack_install
$ cd /path/to/backpack_install

# Install all modules at once
$ ./$script_name -a -d /path/to/laravel/project

# Install one by one
$ ./$script_name -d /path/to/laravel/project

# get help
$ ./$script_name -h

# get version
$ ./$script_name -v

```

[BackupManager optional](https://github.com/Laravel-Backpack/BackupManager#install), you need to configure them.

[For PermissionManager](https://github.com/Laravel-Backpack/PermissionManager#install) to work, add the Spatie\Permission\Traits\HasRoles trait to your User model(s).

## Features

Exit error status:

```
    3:  Error on installing Backpack Core packages
    4:  Error on installing BackupManager
    5:  Error on installing LogManager
    6:  Error on installing Settings
    7:  Error on installing PageManager
    8:  Error on installing PermissionManager
    9:  Error on installing MenuCrud
    10: Error on installing NewsCrud
    11: Error on install FileManager
```

## Author

Shinichi Okada

## Licence

Please see license.txt.
