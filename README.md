# Backpack Installer for macOS/Linux

## Overview

This script automates to install all [Backpack for Laravel modules](https://backpackforlaravel.com/docs/4.1/installation) from your terminal.

Tested on macOS and it should work on Linux.

Installs BackupManager, LogManager, Settings, PageManager, PermissionManager, MenuCrud, and NewsCrud.

![backpack_install demo](https://github.com/shinokada/backpack_install/blob/main/images/backpack-demo.gif?raw=true)

## Requirement

- You must have [Laravel](https://laravel.com/) installed and connected to a database. No data in the database.
- sed

## Usage

- Install laravel

````terminal
$ composer create-project laravel/laravel myproject
``

- Update .env file
- Start Laravel

```terminal
$ php artisan serve
```

- Download or clone this repo to another directory.

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

## Troubleshooting

`backpack_install` file must be executable.

```teminal
$ chmod u+x backpack_install
$ ls -al
drwxr-xr-x 11 shinokada staff   352 May  5 19:36 .
drwxr-xr-x  4 shinokada staff   128 May  5 07:48 ..
drwxr-xr-x 13 shinokada staff   416 May  6 08:04 .git
-rw-r--r--  1 shinokada staff  2833 May  5 08:49 PageTemplates.php
-rw-r--r--  1 shinokada staff  2147 May  6 08:05 README.md
-rwxr--r--  1 shinokada staff 14297 May  5 20:50 backpack_install
-rw-r--r--  1 shinokada staff    39 May  5 20:29 config_app_log.txt
-rw-r--r--  1 shinokada staff   237 May  5 17:38 disk_backup.txt
-rw-r--r--  1 shinokada staff   146 May  5 19:20 disk_logmanager.txt
-rw-r--r--  1 shinokada staff  1070 May  5 07:48 license.txt
-rw-r--r--  1 shinokada staff  1284 May  5 20:44 sidebar_menus.txt
```

## Author

Shinichi Okada

## Licence

Please see license.txt.
