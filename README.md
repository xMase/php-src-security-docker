# PHP Security Docker Image

This project provides a Docker image for building and running PHP with enhanced security settings. It is based on [remicollet/php-src-security](https://github.com/remicollet/php-src-security/tree/PHP-7.4-security-backports) and uses (when possible) the original PHP 7.4 build files from [docker-library/php](https://github.com/docker-library/php).

## Features

- Enhanced security flags and build options
- Minimal Debian base image (debian:bullseye-slim)
- Custom scripts for PHP extension management

## PHP Source Reference

- [remicollet/php-src-security (PHP-7.4-security-backports)](https://github.com/remicollet/php-src-security/tree/PHP-7.4-security-backports)
- [docker-library/php](https://github.com/docker-library/php)

## Included Scripts

The `docker-php-*` scripts are adapted from [docker-library/php](https://github.com/docker-library/php) and modified to work with the new PHP source:

- `docker-php-entrypoint`: Entrypoint script for container startup
- `docker-php-ext-install`: Install PHP extensions
- `docker-php-ext-configure`: Configure PHP extensions
- `docker-php-ext-enable`: Enable PHP extensions
- `docker-php-source`: Manage PHP source extraction and deletion

## Usage

### Build the Image

```bash
docker build -t php-secure .
```

### Run a Container

```bash
docker run -it --rm php-secure
```

### Install Extensions

Inside the container, use:

```bash
docker-php-ext-install mysqli pdo_mysql
```

## License

This project is open source and available under the MIT License.
