# Prestashop on docker-compose

Based on  [PrestaShop/docker](https://github.com/PrestaShop/docker)

## What is this project
`Prestashop docker-compose` is a great way to bootstrap a Prestashop development environmemt.

## How to use it

We recommend to avoid the `PS_INSTALL_AUTO` feature. Instead, copy your own custom installation in `src/`.

For running an existing running website, export your database to a SQL file and paste it in `docker/mariadb/import.sql`. It will be imported to MariaDB when creating the container.

The prestashop image is customized to include Xdebug, higher limits, etc. You can customize the Dockerfile, run `docker-compose build prestashop` and `docker-compose up`.

#### src/config/settings.inc.php
```php
<?php
define('_DB_SERVER_',         getenv('DB_SERVER'));
define('_DB_NAME_',           getenv('DB_NAME'));
define('_DB_USER_',           getenv('DB_USER'));
define('_DB_PASSWD_',         getenv('DB_PASSWD'));
```

### Use this configuration for development/testing, not production