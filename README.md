# Backpack Installer for macOS/Linux

## Overview

This script automates to install all [Backpack for Laravel modules](https://backpackforlaravel.com/docs/4.1/installation) from your terminal.

Tested on macOS and it should work on Linux.

Installs BackupManager, LogManager, Settings, PageManager, PermissionManager, MenuCrud, and NewsCrud.

![backpack_install demo](https://github.com/shinokada/backpack_install/blob/main/images/backpack-demo.gif?raw=true)

## Requirement

- You must have [Laravel](https://laravel.com/) installed and connected to a database. No data in the database.
- gsed

## Installation

### Homebrew

```sh
brew tap shinokada/backpack_install
brew install backpack_install
```

### Clone or download

You can clone or download repo and move to another directory.

```sh
cd /path/to/backpack_install
```

If you have a `~/bin` path in your terminal config (.zshrc, .bash_profile), you can add a symlink.

```sh
ln -sf ~/path/to/your/gitstart ~/bin/gitstart
# e.g.
ln -sf ~/Bash_Projects/Gitstart/gitstart-repo/gitstart ~/bin/gitstart
```

## Set up

1. Install laravel

   ```sh
   composer create-project laravel/laravel myproject
   ```

2. Update .env file.

   If you are using MAMP:

   ```sh
   ...
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=8889
   DB_DATABASE=example_app
   DB_USERNAME=root
   DB_PASSWORD=root
   ...
   ```

3. (Optional) Start Laravel

   ```sh
   php artisan serve
   ```

### Usage

```sh
# Install all modules at once
$ backpack_install -a -d /path/to/laravel/project

# Install one by one
$ backpack_install -d /path/to/laravel/project

Uninstall all modules
$ backpack_install -u -d /path/to/laravel/project

# get help
$ backpack_install -h

# get version
$ backpack_install -v
```

## After installation

- You need to configure [BackupManager optional](https://github.com/Laravel-Backpack/BackupManager#install).

- Add `Spatie\Permission\Traits\HasRoles` trait to your User model(s). See more on [For PermissionManager](https://github.com/Laravel-Backpack/PermissionManager#install).

## After uninstallation

After running uninstallation using `-u` flag, you are recommended running git reset and git clean.

```sh
cd $laravel_dir
git reset --hard
git clean -f -d
```

Clean your database.

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