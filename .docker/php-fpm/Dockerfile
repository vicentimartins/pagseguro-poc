FROM phpdockerio/php74-fpm:latest
WORKDIR "/app"

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y install \
    php7.4-pgsql \
    php7.4-sqlite3 \
    php7.4-curl \
    php-xdebug \
    && apt-get clean;
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# Install git
RUN apt-get update \
    && apt-get -y install git \
    && apt-get clean;
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# add prestissimo
RUN composer global require hirak/prestissimo