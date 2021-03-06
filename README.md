# PHP code quality

[![Build Status](https://travis-ci.org/jasny/php-code-quality.svg?branch=master)](https://travis-ci.org/jasny/php-code-quality)
[![Code Coverage](https://scrutinizer-ci.com/g/jasny/php-code-quality/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/jasny/php-code-quality/?branch=master)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/jasny/php-code-quality/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/jasny/php-code-quality/?branch=master)
[![SensioLabsInsight](https://insight.sensiolabs.com/projects/72d0ff50-daa3-4f2c-91ab-bf5c2397e899/mini.png)](https://insight.sensiolabs.com/projects/72d0ff50-daa3-4f2c-91ab-bf5c2397e899)


## Coding standard

The [Jasny PHP coding standard](https://github.com/jasny/php-code-quality/blob/master/STANDARD.md#readme) follows the PSR-2 coding standard with a few additions.


## Installation

All PHP projects of Legal Things should include this package. It can be installed through composer.

    composer require --dev jasny/php-code-quality


## Toolchain

### PHPUnit
[PHPUnit](https://phpunit.de/) is a programmer-oriented testing framework for PHP. The unit tests should be in the `tests` directory.

Copy the PHPUnit configuration into the projects root folder

    cp vendor/jasny/php-code-quality/phpunit.xml.dist .

### vfsStream
[vfsStream](https://github.com/mikey179/vfsStream) is a stream wrapper for a virtual file system that may be helpful in unit tests to mock the real file system.

### PHP_CodeSniffer
[phpcs](https://github.com/squizlabs/PHP_CodeSniffer) tokenises PHP files and detects violations of a defined set of coding standards. It is an essential development tool that ensures your code remains clean and consistent.
This package comes with a custom ruleset which embodies the Jasny PHP coding standard.

    vendor/bin/phpcs . --standard=vendor/jasny/php-code-quality --ignore=/vendor/,/tests/

CodeSniffer is able to fix simple issues automatically

    vendor/bin/phpcbf . --standard=vendor/jasny/php-code-quality --ignore=/vendor/,/tests/

### Codecoption (applications only)
[Codeception](http://codeception.com/) is a BDD style testing frameworks for PHP. It can be used for unit, functional and integration tests.

The [Codeception module for Jasny MVC] allows you to run tests for applications that use Jasny MVC.

Codeception isn't installed by default. It can be installed through composer.

    composer require --dev codeception/codeception jasny/codeception-module


## Services

### Travis
[Travis CI](https://travis-ci.org) will run all tests on each pull-request and push to the master branch.

Copy the Travis CI configuration file from the php-code-quality directory.

    cp vendor/jasny/php-code-quality/travis.yml.dist .travis.yml

_This service is only used for open-source projects._

### Scrutinizer
[Scrutinizer](https://scrutinizer-ci.com/) tests code quality.

_Scrutizer is also used for building and running tests for Jasny's closed source projects._

### SensioLabsInsight
[SensioLabsInsight](https://insight.sensiolabs.com) gives automatic and unique advise for increasing code quality.

_This service is only used for open-source projects._

