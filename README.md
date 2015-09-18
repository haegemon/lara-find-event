# LaraFindEvent
Small library that enabled after find event at laravel

## Installation

Require this package in your `composer.json` file:

`"haegemon/lara-find-events": "dev-master"`

...then run `composer update` to download the package to your vendor directory.

## Usage

The feature is exposed through a trait that add new functionality to object. Event handler can be describe any standart way. For example we could create a Photos model like this:

```php

use Eloquent\LaraFindEvents\LaraFindEvents as LaraFindEvents;

class Photo extends Eloquent
{
    use LaraFindEvents;
    
    public static function boot()
    {
        parent::boot();
    
        static::found(function (WildPlant $wildPlant) {
            var_dump('Iamfound', $wildPlant->id);
            return true;
        });
    }
}
```