#++++++++++++++++++++++++++++++++++++++
# Debian 9 PHP Docker container
#++++++++++++++++++++++++++++++++++++++

FROM webdevops/base-app:debian-9
MAINTAINER info@webdevops.io
LABEL vendor=WebDevOps.io
LABEL io.webdevops.layout=6
LABEL io.webdevops.version=0.23.0

# Install tools
RUN /usr/local/bin/apt-install \
        imagemagick \
        graphicsmagick

# Install php
RUN /usr/local/bin/apt-install \
        php7.0-cli \
        php7.0-fpm \
        php7.0-json \
        php7.0-intl \
        php7.0-curl \
        php7.0-mysql \
        php7.0-mcrypt \
        php7.0-gd \
        php7.0-sqlite3 \
        php7.0-ldap \
        php7.0-opcache \
        php7.0-xmlrpc \
        php7.0-xsl \
        php7.0-bz2 \
        php-redis \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer

# Deploy scripts/configurations
COPY conf/ /opt/docker/
RUN bash /opt/docker/bin/control.sh provision.role.bootstrap webdevops-php \
    && bash /opt/docker/bin/bootstrap.sh

EXPOSE 9000

CMD ["supervisord"]
