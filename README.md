# Neuger Pantheon Workflow Test

[![CircleCI](https://circleci.com/gh/neuger-digital-team/neuger-workflow-test.svg?style=shield)](https://circleci.com/gh/neuger-digital-team/neuger-workflow-test)
[![Dashboard neuger-workflow-test](https://img.shields.io/badge/dashboard-neuger_workflow_test-yellow.svg)](https://dashboard.pantheon.io/sites/f80c3f9a-1115-459f-a221-2efe4a8baa6a#dev/code)
[![Dev Site neuger-workflow-test](https://img.shields.io/badge/site-neuger_workflow_test-blue.svg)](http://dev-neuger-workflow-test.pantheonsite.io/)

## Links
Pantheon blog article and workflow instructions:
* https://pantheon.io/blog/announcing-pantheons-circleci-orb
* https://github.com/pantheon-systems/example-wordpress-composer
* https://github.com/pantheon-systems/terminus-build-tools-plugin/

Links to create personal access tokens for this project:
* https://github.com/settings/tokens
* https://circleci.com/account/api

## Getting started
Create a new directory for your site.

In that directory, call the following commands:
```
curl -O https://raw.githubusercontent.com/pantheon-systems/terminus-installer/master/builds/installer.phar
php installer.phar install
```

Make sure composer is installed:
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

Then add in a composer.json file into your directory with at least the following in it:
```
{
    "require": {
        "pantheon-systems/terminus": "1.9.0"
    }
}
```
Then execute:
```
composer update
```

## Setting up a new site
In your new directory, execute the following code. You will have to update the site name since this creates a new Pantheon site and the two can't be the same.
```
terminus build:project:create --team="Neuger Communications Group" pantheon-systems/example-wordpress-composer neuger-workflow-test --test-site-name="Neuger Workflow Test" --org="neuger-digital-team"
```

## Working locally with Lando
Follow these instructions:
* https://github.com/pantheon-systems/example-wordpress-composer#working-locally-with-lando
