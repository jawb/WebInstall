#!/bin/bash

if [[ $EUID -ne 0 ]]; then
    echo "You must be a root user" 2>&1
    exit 1
else
    # Add repositories
    add-apt-repository ppa:chris-lea/node.js
    apt-get update

    # Install download & buils tools
    apt-get install build-essential chrpath git-core libssl-dev libfontconfig1-dev curl

    # Install LAMP
    apt-get install tasksel
    tasksel install lamp-server
    apt-get install php5-mysql php5-curl php5-mbstring php5-gd php5-intl php-pear php5-imagick php5-xcache php5-imap php5-mcrypt php5-memcache php5-ming php5-ps php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl
    apt-get install phpmyadmin
    a2enmod rewrite
    service apache2 restart

    # Install ruby
    apt-get install ruby
    apt-get install rubygems

    # Install Sass & Compass
    gem install compass

    # Install node.js & npm
    apt-get install nodejs npm
    npm install express
    npm install socket.io

    # Install CoffeeScript
    npm install coffee-script

    # Install Yeoman
    apt-get install libjpeg-turbo-progs
    apt-get install optipng
    git clone git://github.com/ariya/phantomjs.git
    cd phantomjs
    git checkout 1.7
    ./build.sh && deploy/package.sh
    npm install -g yeoman
fi
