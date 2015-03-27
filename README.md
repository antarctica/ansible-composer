# Composer (`composer`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs Composer package manager as a global utility

## Overview

* Installs Composer PHP phar package
* Copies `composer.phar` to `/usr/local/bin/composer` for global availability
* Adds user aliases to allow transparent access to PHP functions usually restricted

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Usage

### Requirements

#### BAS Ansible Role Collection (BARC)

* `php`

### Limitations

Due to security restrictions imposed by the `php` role the *allow_url_fopen* configuration option is disabled by default.
Composer requires this option to be enabled to operate correctly.

To workaround this additional command line arguments need to be used when using composer:

```shell
php -d allow_url_fopen=1 /usr/local/bin/composer
```

If using the *controller* or *app* users, enabled by default by the `core` role, a suitable alias for the modified composer command will be setup for you.

This means, when using either of these users, composer can be used as normal (e.g. `composer install` will just work). For any other user either a similar alias will be needed or the full command must be used.

### Variables

* `composer_controller_user_username`
    * The username of the controller user, used for management tasks, if enabled
    * This variable **must** be a valid unix username
    * By default this variable will be over-ridden by the `core_controller_user_username` variable from the `core` role.
    * Default: "controller"
* `composer_controller_user_enabled`
    * If "true" a user for management tasks, termed a controller user, will be configured.
    * By default this variable will be over-ridden by the `core_controller_user_enabled` variable from the `core` role.
    * Default: "true"
* `composer_app_user_username`
    * The username of the app user, used for management tasks, if enabled
    * This variable **must** be a valid unix username
    * By default this variable will be over-ridden by the `core_app_user_username` variable from the `core` role.
    * Default: "app"
* `composer_app_user_enabled`
    * If "true" a user for management tasks, termed a app user, will be configured.
    * By default this variable will be over-ridden by the `core_app_user_enabled` variable from the `core` role.
    * Default: "true"

## Contributing

This project welcomes contributions, see `CONTRIBUTING` for our general policy.

## Developing

### Committing changes

The [Git flow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow/) workflow is used to manage development of this package.

Discrete changes should be made within *feature* branches, created from and merged back into *develop* (where small one-line changes may be made directly).

When ready to release a set of features/changes create a *release* branch from *develop*, update documentation as required and merge into *master* with a tagged, [semantic version](http://semver.org/) (e.g. `v1.2.3`).

After releases the *master* branch should be merged with *develop* to restart the process. High impact bugs can be addressed in *hotfix* branches, created from and merged into *master* directly (and then into *develop*).

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the BAS Web & Applications Team Jira project ([BASWEB](https://jira.ceh.ac.uk/browse/BASWEB)).

## License

Copyright 2015 NERC BAS. Licensed under the MIT license, see `LICENSE` for details.