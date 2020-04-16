# Docker-based Drupal stack

[![Build Status](https://travis-ci.org/wodby/docker4drupal.svg?branch=master)](https://travis-ci.org/wodby/docker4drupal)

## Documentation

Full documentation is available at https://wodby.com/docs/stacks/drupal/local.

## License

This project is licensed under the MIT open source license.

# About B1B
B1B is a set of tools for library visitors to get informed about the field of their interest.

B1B is uses the Docker4Drupal set of docker images optimized for Drupal. Use `docker-compose.yml` file from the [latest stable release](https://github.com/wodby/docker4drupal/releases) to spin up local environment on Linux, Mac OS X and Windows.

* Read the docs on [**how to use**](https://wodby.com/docs/stacks/drupal/local#usage)
* Ask questions on [Slack](http://slack.wodby.com/)
* Follow [@wodbycloud](https://twitter.com/wodbycloud) for future announcements

# Usage
First you need to [install composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

> Note: The instructions below refer to the [global composer installation](https://getcomposer.org/doc/00-intro.md#globally).
You might need to replace `composer` with `php composer.phar` (or similar)
for your setup.

After that you can create the project:
### Step 1
```
git clone git@github.com:inleadmedia/b1b_installer.git
```

### Step 2
```cd b1b_installer```

### Step 3
and run
```
composer install
```

### Step 4
Now the Drupal 8 can be installed.

After the Drupal is installed one can proceed to the site configuration.

### Step 5
Ensure that the config sync directory is set in the ```setting.php``` file. Ensure that the ```$config_directories['sync'] = '../config/sync';``` line is in the file.

### Step 6
Import main configurations of the system. In terminal run
```drush cim --partial```.

### Step 7
Import project configs. In terminal run
```drush csim b1b```.

NOTE: This step is required after each deploy of the site.

### Step 8
Set the default frontpage to ```categories``` view on the ```\admin/config/system/site-information``` page.

## Custom actions

### Install additional dependencies
With `composer require ...` you can download new dependencies to your
installation.

```
cd some-dir
composer require drupal/devel:~1.0
```
