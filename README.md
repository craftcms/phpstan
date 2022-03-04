# PHPStan config for Craft CMS

This package provides a base [PHPStan](https://github.com/phpstan/phpstan) configuration for Craft CMS projects.

To install, run the following commands:

```sh
composer config minimum-stability dev
```

```sh
composer config prefer-stable true
```

```sh
composer require craftcms/phpstan:dev-main --dev
```

Then add a `phpstan.neon` config file to the root of your project:

```neon
includes:
    - vendor/craftcms/phpstan/phpstan.neon

parameters:
    level: 0
    paths:
        - src
```

(See PHPStan’s [Config Reference](https://phpstan.org/config-reference) for a full list of supported config parameters.)

With that in place, you can begin running PHPStan with the following command:

```sh
vendor/bin/phpstan --memory-limit=1G
```

Or define a `phpstan` script in `composer.json`:

```json
{
  "...": "...",
  "scripts": {
    "phpstan": "phpstan --memory-limit=1G"
  }
}
```

And then run PHP stan with:

```sh
composer run-script phpstan
```
