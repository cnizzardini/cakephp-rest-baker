# MixerApi REST

[![Latest Version on Packagist](https://img.shields.io/packagist/v/mixerapi/cakephp-rest-baker.svg?style=flat-square)](https://packagist.org/packages/mixerapi/cakephp-rest-baker)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
[![Build Status](https://travis-ci.org/mixerapi/cakephp-rest-baker.svg?branch=master)](https://travis-ci.org/mixerapi/cakephp-rest-baker)
[![Coverage Status](https://coveralls.io/repos/github/mixerapi/cakephp-rest-baker/badge.svg?branch=master)](https://coveralls.io/github/mixerapi/cakephp-rest-baker?branch=master)

The missing RESTful API toolkit for CakePHP. 

- Bake RESTful API skeletons in seconds with an enhanced bake template.
- Generate route resources with a single command.

## Installation

```bash
composer require mixerapi/cakephp-rest
bin/cake plugin load MixerApiRest
```

Alternatively after composer installing you can manually load the plugin in your Application:

```php
# src/Application.php
public function bootstrap(): void
{
    // other logic...
    $this->addPlugin('MixerApiRest');
}
```

## Bake Usage

Add `--theme RestBaker` to your bake commands.

Examples:
 
```bash
# bake all your controllers
bin/cake bake controller all --theme MixerApi/Rest

# bake a single controller
bin/cake bake controller {ControllerName} --theme MixerApiRest

# you can even bake the entire application still, mixerapi/rest only deals with controller files
bin/cake bake all --everything --theme MixerApiRest
```

## Route Commands


#### `mixerapi:rest create`

Scan your controllers and writes CRUD routes to `config/routes.php`

```bash
bin/cake mixerapi:rest create
```

#### `mixerapi:rest create --plugin {MyPlugin}`

Add the `--plugin` switch to write to `plugins/{YourPlugin}/config/routes.php`

```bash
bin/cake mixerapi:rest create --plugin {MyPlugin}
```

#### `mixerapi:rest create --display`

Displays the routes that can be created, but does not write anything to the filesystem

```bash
bin/cake mixerapi:rest create --display 
```

#### `mixerapi:rest list`

This works similar to `bin/cake routes` but shows only RESTful routes and improves some formatting of information.

```bash
bin/cake mixerapi:rest list
```

## Unit Tests

```bash
vendor/bin/phpunit
```

## Code Standards

```bash
composer check
```
