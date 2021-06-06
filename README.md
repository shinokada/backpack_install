# Backpack Installer for macOS/Linux

## Overview

This script automates to install all [Backpack for Laravel modules](https://backpackforlaravel.com/docs/4.1/installation) from your terminal.

Tested on macOS and it should work on Linux.

Installs BackupManager, LogManager, Settings, PageManager, PermissionManager, MenuCrud, and NewsCrud.

[Medium Article](https://codeburst.io/installing-backpack-for-laravel-modules-with-a-line-of-command-eda01d72639f)

## Installation

### macOS

```sh
brew tap shinokada/backpack_install
brew install backpack_install
```

### awesome for Linux

Install [awesome script package manager](https://github.com/shinokada/awesome):

```sh
sudo apt install curl
curl -s https://raw.githubusercontent.com/shinokada/awesome/main/install | bash -s install
# Add ~/bin to PATH variable
echo export PATH='$HOME/bin:$PATH' >> ~/.bashrc
```

Install `backpack_install`:

```sh
awesome install backpack_install
# check the version
backpack_install -v
```

## Set up

1. Install Laravel

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

## Usage

```sh
# Install all modules at once
composer create-project laravel/laravel myproject
cd myproject
backpack_install

# Install one by one
backpack_install -p

# If you want to set dir
backpack_install -d /path/to/myproject


# Uninstall all modules
backpack_install -u
# or with -d
backpack_install -u -d /path/to/laravel/project

# get help
backpack_install -h

# get version
backpack_install -v
```

## After installation

- You need to configure [BackupManager optional](https://github.com/Laravel-Backpack/BackupManager#install).

- Add `Spatie\Permission\Traits\HasRoles` trait to your User model(s). See more on [For PermissionManager](https://github.com/Laravel-Backpack/PermissionManager#install).

## After uninstallation

After running uninstallation using `-u` flag, you are recommended to run `git reset` and `git clean`.

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

## License

Please see license.txt.
