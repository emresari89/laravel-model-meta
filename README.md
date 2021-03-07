# Laravel Meta

[![Latest Version on Packagist](https://img.shields.io/packagist/v/appstract/laravel-model-meta.svg?style=flat-square)](https://packagist.org/packages/emresari89/laravel-model-meta)
[![Total Downloads](https://img.shields.io/packagist/dt/appstract/laravel-model-meta.svg?style=flat-square)](https://packagist. org/packages/emresari89/laravel-model-meta)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/appstract/laravel-model-meta/master.svg?style=flat-square)](https://travis-ci.
org/emresari89/laravel-model-meta)

Metadata for your Eloquent model

## Installation

You can install the package via composer:

```bash
composer require emresari89/laravel-model-meta
```

### Publish, migrate

By running `php artisan vendor:publish --provider="Emresari\Meta\MetaServiceProvider"` in your project all files for this package will be published. 
For this package, it's only a migration. Run `php artisan migrate` to migrate the table. There will now be a table named `metas` in your database.

## Usage

You can easily add Meta to an Eloquent model. Just add this to your model:

```php
use Emresari\Meta\Metable;

class Book extends Model
{
    use Metable;
}
```

Then you can get, add, update and delete meta to the model.

```php
$book = Book::find(1);

$book->addMeta('someKey', 'someValue');

$book->getMeta('someKey');

$book->getMetaValue('someKey');

$book->hasMeta('someKey');

$book->updateMeta('someKey', 'anotherValue');

$book->addOrUpdateMeta('someKey', 'someValue');

$book->deleteMeta('someKey');

$book->getAllMeta();

$book->deleteAllMeta();
```

## Testing

```bash
$ composer test
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
