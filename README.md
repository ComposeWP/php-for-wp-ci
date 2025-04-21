# Minimal PHP Docker Images for WordPress Development

This repository provides lightweight PHP-FPM images with all the essential extensions required to run WordPress and most plugins/themes — built using official `php:<version>-fpm-alpine` base images.

Designed for plugin and theme developers who want fast, ready-to-go PHP environments for local dev or CI.

---

## Included PHP Versions

- `8.2`
- `8.3`
- `8.4`

Each version is built and stored under `src/<version>/Dockerfile`.

---

## What’s Inside

Each image includes:

- WordPress-required extensions:
  - `mysqli`, `pdo`, `pdo_mysql`, `zip`, `intl`, `exif`, `gd`
  - **gd** as replacement for **imagick**
- System packages:
  - `git`, `curl`, `mariadb-client`, and dependencies for all extensions

---

## Docker Usage

```sh
docker pull ghcr.io/Hakira-Shymuy/wp-php-env:8.3

# Or use in docker-compose.yml
services:
  php:
    image: ghcr.io/Hakira-Shymuy/wp-php-env:8.3
```