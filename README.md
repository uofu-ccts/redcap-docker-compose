# REDCap Docker Compose Environment

![Docker Compose][docker-compose-logo]
![REDCap][redcap-logo]

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [About](#about)
- [Features](#features)
- [Quick-Start](#quick-start)
- [Full Documentation](#full-documentation)
- [Updates](#updates)
- [License](#license)
- [Contributing](#contributing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

[![documentation-button](rdc/documentation/button_documentation.png)](rdc/documentation/README.md)


## About
This repo is designed to build a local development instance of REDCap on your laptop.  It also includes some aids
to try and facilitate a rapid setup of REDCap using either your consortium credentials or a complete installer you
receive from a teammate at your institution.

This is intended to be one of the fastest and easiest ways to create a local development instance of REDCap on your
computer or test server.

This is not intended to be used as a production server, although we do run something pretty similar here at Stanford.
Should you want to run this as production, be sure to edit the `redcap.ini` file in the `override-web/php` folder
to have production-ready php settings.

## Features
 * Mailhog to capture outbound email for review
 * X-Debug support for detailed server-side inspection
 * PhpMyAdmin support for easy database maintenance / backups / restores
 * Easy to modify php-version or mysql-version and rebuild your environment in minutes

## Quick-Start
 * [Install Docker Desktop](https://docs.docker.com/get-docker) (requires docker account which is free)
 * [Download this repository](https://github.com/123andy/redcap-docker-compose/archive/master.zip) and unzip it to your computer
 * Open your download directory using a good IDE (
 [phpStorm](https://www.jetbrains.com/phpstorm/),
 [Visual Studio Code](https://code.visualstudio.com/),
 [Atom](https://atom.io/) - does not support xdebug, etc... )
 * Copy/Rename the `.env-example` to make a `.env` file - it is located in the `rdc` folder review the contents, making changes as necessary.
 * (One time) - You may need to enable privileged port mapping in Docker Desktop
   * Docker -> Setttings -> Advanced -> Enable privileged port mapping
 * Once `.env` file settings are correct, from the `rdc` folder type `docker compose up -d`
 * Open your web browser and goto `http://localhost` (or, in some cases with macs `http://127.0.0.1`) and follow
  directions for further installation
   * (Initial build) - you will need to download the RedCAP code on initial build.  Use the BMIC general user and 
   password. Available from the Keepass file username: u7ah.r3dcap
   * Only use the default community account to ask questions after all department resources have been tried

:warning: **If you have a previous version of redcap-docker-compose make sure you change the `DOCKER_PREFIX` variable otherwise you may corrupt your existing installation.  Please see the full docs for more detail**

## Upgrading The Framework
If you have an existing REDCap Docker Compose development setup and wish to swtich to the latest version, please review
the section in the [detailed documentation](rdc/documentation/README.md#how-do-i-upgrade-to-the-latest-version-of-redcap-docker-compose)

## Full Documentation
See the [detailed documentation](rdc/documentation/README.md) for more information!  Keep in mind this is a community
effort so feedback is appreciated.  Please create issues here with any suggestions or make a pull request with improvements.

## Updates
* 2022-10-06  Did some cleanup to allow for M1 (ARM) support and Intel without changes
* 2022-02-16  Made defaults php 8.1, mysql 8.0, xdebug 3.1.3 and incorporated some pull requests
* 2020-12-28  Made defaults php7.4, xdebug 3.0, mysql 8
* 2020-09-24  Minor documentation cleanup and testing for Windows
* 2019-10-03  Improved documentation and cleanup of unused settings (issue #4)
* 2019-09-06  Removed ssmtp and replaced with msmtp
* 2019-06-06  Add X-Debug configuration.
* 2019-01-24  Changed folder layout and optimized unzipping after upload to be much faster
* 2018-08-19  Added .env file and added UID override for MAC users to maintain file ownership (see .env)
* 2018-08-04  Added support for auto-install from `redcapx.y.z.zip`
* 2018-08-01  Major refactoring into docker-compose 3

## License
Copyright (c) 2016 Andrew Martin
Licensed under the MIT license.

## Contributing
Please make pull requests to extend the functionality and documentation

I'd like to thank the many people who have contributed to making this repo better!

[redcap-logo]: rdc/documentation/redcap-logo-large.png "REDCap"
[docker-compose-logo]: rdc/documentation/docker-compose.png "Docker Compose"
