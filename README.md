# Backpack Installer for macOS/Linux

## Overview

This script automates to install all [Backpack for Laravel modules](https://backpackforlaravel.com/docs/4.1/installation) from your terminal.

Tested on macOS and it should work on Linux.

Installs BackupManager, LogManager, Settings, PageManager, PermissionManager, MenuCrud, and NewsCrud.

![backpack_install demo](https://github.com/shinokada/backpack_install/blob/main/images/backpack-demo.gif?raw=true)

## Requirement

- You must have [Laravel](https://laravel.com/) installed and connected to a database. No data in the database.
- gsed

## Usage

1. Install laravel

   ```terminal
   composer create-project laravel/laravel myproject
   ```

2. Update .env file

3. (Optional) Start Laravel

   ```terminal
   php artisan serve
   ```

4. Download or clone this repo to another directory.

   ```terminal
   cd /path/to/backpack_install
   ```

Then run one of following commands.

### Examples

```terminal
# Install all modules at once
$ ./backpack_install -a -d /path/to/laravel/project

# Install one by one
$ ./backpack_install -d /path/to/laravel/project

Uninstall all modules
$ ./$script_name -u -d /path/to/laravel/project

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
    4:  Error
```

When you have an error. You can use `echo $?` to output the error code.

## After uninstallation

After running uninstallation using `-u` flag, you are recommended running git reset and git clean.

```terminal
cd $laravel_dir
git reset --hard
git clean -f -d
```

Then clean your database.

Now you can install all modules again.

## Troubleshooting

`backpack_install` files must be executable.

```teminal
chmod u+x backpack_install
chmod -R u+x lib
```

## Author

Shinichi Okada

## Licence

Please see license.txt.

## How to revert your project

```terminal
cd /path/to/laravel
git reset --hard
git clean -f -d
```

Clean the database.
