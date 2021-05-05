# Backpack Installer for macOS/Linux

## Overview

This script automates to install all [Backpack for Laravel modules](https://backpackforlaravel.com/docs/4.1/installation) from your terminal.

Tested on macOS and it should work on Linux.

Installs BackupManager, LogManager, Settings, PageManager, PermissionManager, MenuCrud, and NewsCrud.

## Requirement

- You must have [Laravel](https://laravel.com/) installed and connected to a database. No data in the database.
- sed

## Usage

- Install laravel

````terminal
$ composer create-project laravel/laravel myproject
``

- Update .env file

- Download or clone this repo.

```terminal
$ cd /path/to/backpack_install
````

- Options:

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
$ ./backpack_install -a -d /path/to/laravel/project

# Install one by one
$ ./backpack_install -d /path/to/laravel/project

# get help
$ ./backpack_install -h

# get version
$ ./backpack_install -v

```

## After installation

- You need to configure [BackupManager optional](https://github.com/Laravel-Backpack/BackupManager#install).

- Add `Spatie\Permission\Traits\HasRoles` trait to your User model(s). See more on [For PermissionManager](https://github.com/Laravel-Backpack/PermissionManager#install).

Exit error status:

```terminal
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

When you have an error. You can use `echo $?` to output the error code.

## Author

Shinichi Okada

## Licence

Please see license.txt.
