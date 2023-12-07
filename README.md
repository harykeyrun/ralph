# Ralph

Ralph is full-featured Asset Management, DCIM and CMDB system for data centers and back offices.

Features:

* keep track of assets purchases and their life cycle
* flexible flow system for assets life cycle
* data center and back office support
* dc visualization built-in

It is an Open Source project provided on Apache v2.0 License.

[![Gitter](https://img.shields.io/gitter/room/gitterHQ/gitter.svg)](https://gitter.im/allegro/ralph?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![packagecloud](https://img.shields.io/badge/deb-packagecloud.io-844fec.svg)](https://packagecloud.io/allegro/ralph)
[![Build Status](https://github.com/allegro/ralph/actions/workflows/main.yml/badge.svg)](https://github.com/allegro/ralph/actions/workflows/main.yml)
[![Coverage Status](https://coveralls.io/repos/allegro/ralph/badge.svg?branch=ng&service=github)](https://coveralls.io/github/allegro/ralph?branch=ng)
[![Code Health](https://landscape.io/github/allegro/ralph/ng/landscape.svg?style=flat)](https://landscape.io/github/allegro/ralph/ng)

# Live demo:

http://ralph-demo.allegro.tech/

* login: ralph
* password: ralph

# Screenshots

![img](https://github.com/allegro/ralph/blob/ng/docs/img/welcome-screen-1.png?raw=true)

![img](https://github.com/allegro/ralph/blob/ng/docs/img/welcome-screen-2.png?raw=true)

![img](https://github.com/allegro/ralph/blob/ng/docs/img/welcome-screen-3.png?raw=true)


## Documentation
Visit our documentation on [readthedocs.org](https://ralph-ng.readthedocs.org)

# PART 2 - CMDB INSTALLATION
## SETUP
### Hari K
#### harikiran.cse@gmail.com

#### Installation on Ubuntu 20.x
* Use sudo
* NVM setup and installation
* Update first using apt update
## Download NVM prereq
* Specific version only
  * curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
  * export NVM_DIR="$HOME/.nvm"
  * [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
  * [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
  * nvm install 11.7.0
## Pre-req
* Install additional libraries
  * sudo apt-get install build-essential checkinstall libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev
## Python installation
* Python3.6
  * sudo wget https://www.python.org/ftp/python/3.6.10/Python-3.6.10.tgz
  * wget https://www.python.org/ftp/python/3.6.10/Python-3.6.10.tgz
  * tar xzf Python-3.6.10.tgz
  * cd Python-3.6.10
  * ./configure --enable-optimizations
  * make altinstall
  * Verify next
    * python3.6 -V
    * pip3.6 -V
## Setup and install MYSQL
   * login as root (sample password sql@2023 OR Admin@123!)
     * CREATE DATABASE ralph_ng DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_general_ci;
     * CREATE USER 'ralph_ng'@'localhost' IDENTIFIED BY 'Ralph_135!';
     * GRANT ALL PRIVILEGES ON ralph_ng.* TO 'ralph_ng'@'localhost';
     * //-- ALTER USER 'ralph'@'%' IDENTIFIED WITH mysql_native_password BY 'Ralph_135!';
     * flush privileges;
     * exit
## Clone the code 
* https://github.com/harykeyrun/ralph
### Code execution
#### DEV profile setup
  * Go to CMDB repo local folder location after cloning the code. Type the repo name
    *     cd ralph/
    *     pip3.6 install --upgrade pip
    *     pip3.6 install -r requirements/dev.txt “This may fail”
#### Fix the dependencies
     apt-get install libmysqlclient-dev libsasl2-dev python-dev libldap2-dev libssl-dev
  * Go to requirements
    * Edit the file openstack.txt
    *     oslo.utils==3.16.0
    *     keystoneauth1==2.10.0
    *     stevedore==1.16.0
    *     Babel==2.8.0

    * Also edit the file base.txt
    *     pytz==2015.7
    *     Markdown==3.2.1
#### Install mysql client

    * pip3.6 install mysqlclient==1.3.14

    * OR 

    * pip3.6 install mysqlclient
#### More libraries
    *     apt-get install gcc
    *     apt-get install libsasl2-dev python-dev libldap2-dev libssl-dev
#### Try now
    *     pip3.6 install -r requirements/dev.txt “This time it should work”
    *     pip3.6 install -r requirements/docs.txt
#### One more package
    *     apt install python3-devel
    *     NPM installation
    *     npm install 
    *     npm audit fix
#### Build node modules (For every change in the static files)
    *     ./node_modules/.bin/gulp || ./node_modules/bin/gulp
##### COPY from template
    *     cp src/ralph/settings/local.template src/ralph/settings/local.py
##### Verify local settings
    *     nano src/ralph/settings/local.py
#### Export Django settings
    *     export DJANGO_SETTINGS_MODULE="ralph.settings.local"
## Change to root
    *     Sudo -i
    *     Developer setup
    *     python3.6 setup.py develop
### Create schema using the code
    *     dev_ralph migrate
    *     Create super user
    *     dev_ralph createsuperuser
### Execute developer instance
    *     make menu
    *     make run
###### verify on http://localhost:8000



## Getting help

* Online forum for Ralph community: https://ralph.discourse.group
