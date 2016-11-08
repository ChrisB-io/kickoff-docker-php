![alt tag](https://img.shields.io/badge/PHP-7.0.8-green.svg) ![alt tag](https://img.shields.io/badge/Composer-1.2.2-green.svg) ![alt tag](https://img.shields.io/badge/MySQL-5.7.13-green.svg) ![alt tag](https://img.shields.io/badge/Node.js-4.6.1-orange.svg) ![alt tag](https://img.shields.io/badge/npm-2.15.9-orange.svg)

# Goal

This project will help you starting a PHP project with Docker, thanks to some useful make commands.

# Prerequisites

Install Docker (**>= 1.10**) for MacOSX / Linux following the official instructions: https://docs.docker.com/engine/installation

Install docker-compose (**>= 1.8.0**) for MacOSX / Linux following the official instructions: https://docs.docker.com/compose/install

**Important: for now, we do not recommend using Windows.**

# Quick start

First, fork this project and clone it.

Once done, move to the root directory of this project and run:

```
cp Makefile.default Makefile
```

Open your freshly created `Makefile` in your favorite editor and update the following environment variables:

```
PROJECT_NAME=yourproject
DATABASE_NAME=database_name
ENV=dev
ENV_DOMAIN_NAME=dev.yourproject.com
WITH_XDEBUG=0
```

**Note:** if `WITH_XDEBUG=1`, it will enable Xdebug on the apache container. We also recommend to enable it only for your development environment!

Good? Now open the file located at `/etc/hosts` (on MacOS / Linux) and add the following line at the end of the file:

```
127.0.0.1   dev.yourproject.com
```

**Note:** please make sure that the domain name matches the value defined for `ENV_DOMAIN_NAME`.
 
We're now done with the configuration! :metal:

Last but not least, shutdown your local apache or anything which could use your 80 and 443 ports, and run:

```
make kickoff
```

The installation might take some time, so go for a coffee break! :coffee: 

Once everything has been installed, open your favorite web browser and copy / paste http://dev.yourproject.com and check if everything is OK!