# Acredula\Support

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Total Downloads](https://img.shields.io/packagist/dt/hmsweb/support.svg?style=flat-square)](https://packagist.org/packages/hmsweb/support)

Support package providing commonly used packages via service providers and inflectors.

All Service Providers require [league/container](https://packagist.org/packages/league/container) >=2.*.

### ConfigServiceProvider

```php
use Acredula\Support\ServiceProvider\ConfigServiceProvider;

$container->addServiceProvider(new ConfigServiceProvider([
    'path' => __DIR__ . '/../config/config.php',
    'env'  => __DIR__ . '/../.env'
]));
```

##### Dependencies

* [gorka/dot-notation-access](https://packagist.org/packages/gorka/dot-notation-access)
* [josegonzalez/dotenv](https://packagist.org/packages/josegonzalez/dotenv)

### AuraSqlServiceProvider

```php
use Acredula\Support\ServiceProvider\AuraSqlServiceProvider;

$container->addServiceProvider(new AuraSqlServiceProvider('mysql'));
```

Database credentials should exist in your `.env` file in the following format.

```
DATABASE_HOST={{ host }}
DATABASE_NAME={{ db_name }}
DATABASE_USER={{ username }}
DATABASE_PASS={{ password }}
```

##### Dependencies

* [aura/sql](https://packagist.org/packages/aura/sql)
* [aura/sqlquery](https://packagist.org/packages/aura/sqlquery)

### SwiftMailerServiceProvider

```php
use Acredula\Support\ServiceProvider\SwiftMailerServiceProvider;

$container->addServiceProvider(new SwiftMailerServiceProvider);
```

##### Dependencies

* [swiftmailer/swiftmailer](https://packagist.org/packages/swiftmailer/swiftmailer)


### TwigServiceProvider

```php
use Acredula\Support\ServiceProvider\TwigServiceProvider;

$container->addServiceProvider(new TwigServiceProvider([
    'templates'  => __DIR__ . '/../templates',
    'cache' => __DIR__ . '/../writable/directory',
    'extensions' => [
        'Acme\Tekkers\UnbelievableTekkersExtension'
        'Acme\Large\LargeGravyExtension'
    ]
]));
```

##### Dependencies

* [twig/twig](https://packagist.org/packages/twig/twig)

### AuraSessionServiceProvider

```php
use Acredula\Support\ServiceProvider\AuraSessionServiceProvider;

$container->addServiceProvider(new AuraSessionServiceProvider);
```

##### Dependencies

* [aura/session](https://packagist.org/packages/aura/session)
