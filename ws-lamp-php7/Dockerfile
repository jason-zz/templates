FROM cloud9/workspace
MAINTAINER Jason Zhang <jason.zhang@internetrix.com.au>

# Supporting tools
RUN apt-get -qqy install sudo wget telnet nano vim curl git bzip2 zip unzip dnsutils iputils-ping net-tools mailutils

# APACHE 
RUN apt-get -qqy install apache2 

## Multi PHP Version Support
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php

RUN apt-get -qq update

RUN apt-get -qqy upgrade

# PHP 7.0
RUN apt-get -qqy install php7.0 php7.0-cli php7.0-fpm php7.0-mysql php7.0-curl php7.0-soap php7.0-common php7.0-gd php7.0-mcrypt php7.0-tidy php7.0-mbstring php7.0-xml php7.0-intl
	
RUN echo "date.timezone = Australia/Sydney" > /etc/php/7.0/cli/conf.d/timezone.ini && \
	echo "date.timezone = Australia/Sydney" > /etc/php/7.0/fpm/conf.d/timezone.ini

# Composer
RUN wget https://getcomposer.org/composer.phar && \
	chmod +x composer.phar && \
	mv composer.phar /usr/local/bin/composer



ADD ./files/workspace /home/ubuntu/workspace

RUN chmod -R g+w /home/ubuntu/workspace && \
    chown -R ubuntu:ubuntu /home/ubuntu/workspace
