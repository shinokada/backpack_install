<p align="center">
<img width="400" src="https://raw.githubusercontent.com/shinokada/backpack_install/main/images/backpack_install.png" />
</p>
<h1  align="center">Backpack Installer for macOS/Linux</h1>

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

### Using Awesome Package Manager for Linux

After installing [awesome script package manager](https://github.com/shinokada/awesome):

```sh
awesome -i shinokada/backpack_install
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

Start Laravel.

```sh
php artisan serve
```

Visit http://127.0.0.1:8000/admin/login or http://127.0.0.1/admin/login depending the port you are using.


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

MIT License

Copyright (c) 2018 Fábio Maia

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
