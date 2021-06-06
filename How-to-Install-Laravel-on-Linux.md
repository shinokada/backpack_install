# How to install Laravel on Linux

```sh
sudo apt update
sudo apt install php-cli unzip
cd ~
curl -sS https://getcomposer.org/installer -o composer-setup.php
HASH=`curl -sS https://composer.github.io/installer.sig`
# Check HASH
echo $HASH
php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
# Check if it installed
composer
# Install mbstring
apt search mbstring
sudo apt install php-mbstring
mkdir Laravel
cd Laravel
composer create-project laravel/laravel myproject
```
