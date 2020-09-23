# Jetstrap

[![Latest Stable Version](https://poser.pugx.org/nascent-africa/jetstrap/v)](//packagist.org/packages/nascent-africa/jetstrap)
[![License](https://poser.pugx.org/nascent-africa/jetstrap/license)](//packagist.org/packages/nascent-africa/jetstrap)

## Description

[Laravel Jetstream](https://github.com/laravel/jetstream) is a wonderful upgrade from Laravel UI, however it does not come with an option to use Bootstrap scaffolding out of the box instead your given a single option of TailwindCSS. Tailwind is an excellent framework but for folks with a long-standing relationship with Bootstrap it may be difficult to make the sudden switch.

Jetstrap is built to target the `VIEW` side of [Jetstream](https://github.com/laravel/jetstream) installed in your Laravel application, so when a swap is performed, the `MODEL` and `CONTROLLER` portion of your project is still 100% Jetstream with no added layer of complexity.

This package makes use of Bootstrap 5 even though its still in alpha version because just like TailwindCSS, it leans towards utility classes, and by dropping jQuery as a dependency it gives room for AlpineJs, so instead of a #TALL stack, you would have a #BALL stack. Before proceeding please checkout the [Bootstrap 5](https://v5.getbootstrap.com/docs/5.0/getting-started/introduction/) documentation for more details.

## Installation

After installing and configuring Laravel Jetstream, install Jetstrap in your project via composer:

```
composer require nascent-africa/jetstrap --dev
```

### Choosing a Bootstrap version

Jetstrap supports two different versions of Bootstrap, version 4 and 5. Version 5 is set as the default version, 
but you can easily switch to version 4 by using the `JetstrapFacade` in your service provider before performing a swap:

```php
<?php

namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use NascentAfrica\Jetstrap\JetstrapFacade;

class AppServiceProvider extends ServiceProvider
{
    /**
     * Register any application services.
     *
     * @return void
     */
    public function register()
    {
        //
    }

    /**
     * Bootstrap any application services.
     *
     * @return void
     */
    public function boot()
    {
        JetstrapFacade::bootstrap4();
    }
}
```

Regardless how you install Jetstream. Jetstrap command is very similar to that
of Jetstream as it accepts the name of the stack you prefer (livewire or inertia).

> It is important you install and configure [Laravel Jetstream](https://github.com/laravel/jetstream) before performing a swap.

You are highly encouraged to read through the entire documentation of [Jetstream](https://jetstream.laravel.com/1.x/introduction.html)
before beginning your Jetstrap project. In addition, you may use the `--teams` switch to swap team assets just like you would in Jetstream:

```bash

php artisan jetstrap:swap livewire

or

php artisan jetstrap:swap livewire --teams

php artisan jetstrap:swap inertia --teams
```

This will publish overrides in the `views/vendor/Jetstream` directory and a few familiar files to enable Bootstrap like the good old days!

Remove tailwindCSS and its dependencies from your package.json file and proceed by doing the following:

```bash

npm install

npm run watch
``` 

## License
Jetstrap is open-sourced software licensed under the [MIT license](https://github.com/nascent-africa/jetstrap/blob/master/LICENSE).

## Long Live Bootstrap!
