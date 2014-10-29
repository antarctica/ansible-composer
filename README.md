# Composer (`composer`)

**Part of the BAS Ansible Role Collection (BARC)**

Installs Composer package manager as a global utility

## Overview

* Installs Composer PHP phar package
* Copies `composer.phar` to `/usr/local/bin/composer` for global availability 

## Author

[British Antarctic Survey](http://www.antarctica.ac.uk) - Web & Applications Team

Contact: [basweb@bas.ac.uk](mailto:basweb@bas.ac.uk).

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Branches

This project uses three permanent branches with the *Git Flow* branching model managing the interaction between branches.

* **Develop:** unstable, potentially non-working but most current version of roles. Bug fixes and features interact with this branch only.
* **Master:** stable, tested, working version of role with full documentation. Releases and hot fixes mainly interact with this branch. This branch should when consuming roles internally.
* **Public:** equivalent to the *master* branch, but available externally. Some configuration details may be altered or features removed to make available for public release.

## Testing

Manual testing is performed for all roles to ensure roles achieve their aims and this forms a prerequisite task for merging changes into the *master* and *public* branches.
Wherever possible testing is as complete as possible meaning tasks such as downloading dependencies are performed as part of each test.

## Issues

Please log issues to the [BAS Web and Applications Team](https://jira.ceh.ac.uk/browse/BASWEB) project in Jira, within the *Project - Ansible Roles* component.

If outside of NERC please get in touch to report any issues.

## Contributions

We have no formal contribution policy, if you spot any bugs or potential improvements please submit a pull request or get in touch.

These roles are used for internal projects which may dictate whether any contributions can be included.

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### BAS Ansible Role Collection (BARC)

* `php`

### Variables

* `composer_controller_user_username`
    * The username of the controller user, used for management tasks, if enabled
    * This variable **must** be a valid unix username
    * Default: "controller"

## Changelog

### 0.1.4 - October 2014

* Updating dependencies
* Controller username can now be configured using a variable
* Preparing for public release

### 0.1.3 - October 2014

* Fixing README

### 0.1.2 - October 2014

* Adjusting role for inclusion in BARC

### 0.1.1 - September 2014

* Ensures system wide install location exists before moving there

### 0.1.0 - September 2014

* Initial version
