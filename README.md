# TDDD - Test Driven Development Dashboard
### A Self-Hosted TDD Dashboard & Tests Watcher 

[![Latest Stable Version](https://img.shields.io/packagist/v/pragmarx/tddd.svg?style=flat-square)](https://packagist.org/packages/pragmarx/tddd)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md) 
[![Downloads](https://img.shields.io/packagist/dt/pragmarx/tddd.svg?style=flat-square)](https://packagist.org/packages/pragmarx/tddd) 
[![Code Quality](https://img.shields.io/scrutinizer/g/antonioribeiro/tddd.svg?style=flat-square)](https://scrutinizer-tddd.com/g/antonioribeiro/tddd/?branch=master) 
[![Build](https://img.shields.io/scrutinizer/build/g/antonioribeiro/tddd.svg?style=flat-square)](https://scrutinizer-tddd.com/g/antonioribeiro/tddd/?branch=master) 
[![StyleCI](https://styleci.io/repos/27037779/shield)](https://styleci.io/repos/27037779)

## What is it?

The TDD Dashboard is a versatile application designed as a Laravel PHP package, specifically tailored to facilitate Test-Driven Development (TDD) workflows. It serves as a comprehensive tool for developers to manage and monitor their tests while actively coding. It comprises of several features and functionality such as 

1. Test Framework Compatibility 
The TDD Dashboard is engineered to be test framework agnostic. Accommodating a wide range of test frameworks that operate in a terminal environment. This flexibility allows developers to seamlessly integrate their preferred testing tools into their workflow.

2. Out-Of-The-Box-Testers
The dashboard comes preconfigured with several popular testing frameworks, including PHPUnit, phpspec, behat, Jest, and AVA. This preconfiguration simplifies the setup process for commonly used testing environments.

3. Custom Test Integration
Developers can easily incorporate their own testing tools by providing the path to the executable. This means that regardless of your project's specific testing requirements, you can configure the dashboard to support them effortlessly.

4. Progress Monitoring
The TDD Dashboard offers a visual representation of test progress, making it easy to track the status of your tests. This visual feedback enables developers to identify failing tests quickly and monitor overall test suite execution.

5. Screenshot Display
If your chosen test framework generates screenshots during testing, the TDD Dashboard has the capability to display these images within the log page. This visual representation retains the familiar red and green indicators that developers are accustomed to seeing in their terminal output.

In conclusion, the TDD Dashboard is a feature-rich application that enables developers to quickly adopt a strong TDD methodology. It supports a wide range of test frameworks, assures smooth code editor integration, and offers crystal-clear visual feedback on test progress. Additionally, its adaptability to the particular requirements of your project is made possible by its flexibility in integrating custom test tools, thus boosting your capacity to develop trustworthy and maintainable code while adhering to the TDD technique.


* [PHPUnit](https://phpunit.de/)
* [Laravel & Laravel Dusk](https://laravel.com/docs/5.5/dusk)
* [Codeception](http://codeception.com/)
* [phpspec](http://www.phpspec.net/en/stable/)
* [Behat](http://behat.org/en/latest/)
* [atoum](http://atoum.org/)
* [Jest](https://facebook.github.io/jest/)
* [AVA](https://github.com/avajs/ava)
* [React](https://reactjs.org/)
* [Ruby on Rails](http://guides.rubyonrails.org/testing.html)
* [Nette Tester](https://tester.nette.org/)
* [Symfony](https://symfony.com/doc/current/testing.html)

## Features

* Project List: click a project link to see all its tests.
* Open files directly in your source code editor (PHPStorm, Sublime Text...).
* Error log with source code linked, go strait to the error line in your source code.
* Enable/disable a test. Once disabled if the watcher catches a change in resources, that test will not fire.
* Real time test state: "idle", "running", "queued", "ok" and "failed".
* "Show" button, to display the error log of failed tests.
* Highly configurable, watch anything and test everything!
 
### Videos

- [Preview](https://www.youtube.com/watch?v=sO_aDf3xCgE)
- [Installing](https://youtu.be/AgkKCLNiV8w)
- [VueJS Preview](https://youtu.be/HAdfLYArk_A)
- [Laravel Dusk Preview](https://youtu.be/ooF4oLD9U7Q)

### Screenshots

#### Dashboard

![visits](https://raw.githubusercontent.com/antonioribeiro/tddd/master/docs/dashboard.png)

#### Error Log
![visits](https://raw.githubusercontent.com/antonioribeiro/tddd/master/docs/errorlog1.png)

![visits](https://raw.githubusercontent.com/antonioribeiro/tddd/master/docs/errorlog2.png)

![visits](https://raw.githubusercontent.com/antonioribeiro/tddd/master/docs/errorlog3.png)

## Command Line Interface

The Artisan commands **Watcher** and **Tester** are responsible for watching resources and firing tests, respectively:

### Watcher

Keep track of your files and enqueue your tests every time a project or test file is changed. If a project file changes, it will enqueue all your tests, if a test file changes, it will enqueue only that particular test. This is how you run it:

``` bash
php artisan tddd:watch
```

### Tester

Responsible for taking tests from the run queue, execute it and log the results. Tester will only execute enabled tests. This is how you run it:

``` bash
php artisan tddd:test
```

### Notifications

It uses JoliNotif, so if it's not working on macOS, you can try installing terminal-notifier:

``` bash
brew install terminal-notifier
```

## Test Framework Compatibility

This package was tested and is known to be compatible with

* [Codeception](http://codeception.com/)
* [PHPUnit](https://phpunit.de/)
* [phpspec](http://www.phpspec.net/)
* [behat](http://docs.behat.org/)
* [atoum](https://github.com/atoum/atoum)
* [Nette Tester](http://tester.nette.org/en/)


## Requirements

- Laravel 4.1+ or 5
- PHP 5.3.7+

## Installing
#### Manually
Install php version first
php version 7.1.0 : https://prototype.php.net/versions/7.1.0/
Install Composer next 
composer 2.6.2 : https://www.javatpoint.com/how-to-install-composer-on-windows#:~:text=Updating%20and%20Uninstalling%20Composer&text=From%20there%2C%20you%20can%20verify,ready%20for%20the%20next%20steps.
Install Laravel next
laravel V4.2 : https://laravel.com/docs/4.2
 

#### TL;DR

``` bash
laravel new tddd
cd tddd
composer require pragmarx/tddd
php artisan vendor:publish --provider="PragmaRX\Tddd\Package\ServiceProvider"
valet link tddd
# configure database on your .env
php artisan migrate
php artisan tddd:watch & php artisan tddd:work &
open http://tddd.dev/tests-watcher/dashboard
``` 

### Examples & Starter App

For lots of examples, check [this starter app](https://github.com/antonioribeiro/tests-watcher-starter), which will also help you create an independent dashboard for your tests.

### The long version

Require it with [Composer](http://getcomposer.org/):

``` bash
composer require pragmarx/tddd
```

Create a database, configure on your Laravel app and migrate it

``` bash
php artisan migrate
```

Publish Ci configuration:

On Laravel 4.*

Add the service provider to your app/config/app.php:

``` php
'PragmaRX\Tddd\Package\ServiceProvider',
```

``` bash
php artisan config:publish pragmarx/tddd
```

On Laravel 5.*

``` bash
php artisan vendor:publish --provider="PragmaRX\Tddd\Package\ServiceProvider"
```

## Example of projects

### Laravel Dusk

``` php
'project bar (dusk)' => [
    'path' => $basePath,
    'watch_folders' => [
        'app',
        'tests/Browser'
    ],
    'exclude' => [
        'tests/Browser/console/',
        'tests/Browser/screenshots/',
    ],
    'depends' => [],
    'tests_path' => 'tests',
    'suites' => [
        'browser' => [
            'tester' => 'dusk',
            'tests_path' => 'Browser',
            'command_options' => '',
            'file_mask' => '*Test.php',
            'retries' => 0,
        ],
    ],
],
```

## Troubleshooting

#### Tests are running fine in terminal but failing in the dashboard? 

You have first to remember they are being executed in isolation, and, also, the environment is not exactly the same, so things like a cache and session may affect your results. 

## Author

[Antonio Carlos Ribeiro](http://twitter.com/iantonioribeiro)

## License

Laravel Ci is licensed under the BSD 3-Clause License - see the `LICENSE` file for details

## Contributing

Pull requests and issues are welcome.



<!-- [![Coverage](https://img.shields.io/scrutinizer/coverage/g/antonioribeiro/tddd.svg?style=flat-square)](https://scrutinizer-tddd.com/g/antonioribeiro/tddd/?branch=master) --> 
