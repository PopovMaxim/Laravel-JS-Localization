Laravel JS Localization
=======================

> Laravel Localization in JavaScript.

This is a simple package that convert all your localization messages of your Laravel app to JavaScript, and provides a small JavaScript library to interact with those messages.

Installation
------------

Add the following line to you `composer.json` file under `require`.

    "mariuzzo/laravel-js-localization": "1.0.*"

Run:

    composer update

In your Laravel app go to `app/config/app.php` and add the following service provider:

    'providers' => array(
        ...
        'Mariuzzo\LaravelJsLocalization\LaravelJsLocalizationServiceProvider'
        ...
    )

That's it!

Usage
-----

This project comes with a command that generate the JavaScript version of all your messages found at: `app/lang` directory. The resulting JavaScript file will have the whole bunch of messages and a thin library similar to Laravel's `Lang` class.

**Generating JS messages**

    php artisan lang:js

**Specifying a custom target**

    php artisan lang:js public/assets/dist/lang.dist.js

**Compressing the JS file**

    php artisan lang:js -c

Documentation
-------------

This is the documentation regarding the thin JavaScript library. The library highly inspired on Laravel's `Lang` class.

**Getting a message**

    Lang.get('messages.home');

**Getting a message with replacements**

    Lang.get('messages.welcome', { name: 'Joe' });

**Changing the locale**

    Lang.setLocale('es');

**Checking if a message key exists**

    Lang.has('messages.foo');

For more detailed information, take a look at the source: [Lang.js](https://github.com/rmariuzzo/Laravel-JS-Localization/blob/develop/js/lang.js).

Want to contribute?
===================

 1. Fork this repository and clone it.
 2. Create a branch from develop: `git checkout -b feature-foo`.
 3. Push your commits and create a pull request.
