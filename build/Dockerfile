FROM phpdockerio/php56-fpm:latest

    #&& apt-get -y --no-install-recommends install php5-ldap  php5-memcached php5-mysql php5-adodb php5-gd php5-memcache \
# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install bzip2 php5-ldap php5-mysql php5-adodb php5-gd php5-memcache \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

COPY packages /packages
COPY dpj /usr/local/bin
RUN chmod a+x /usr/local/bin/dpj

COPY php-ini-overrides.ini /etc/php5/fpm/conf.d/99-overrides.ini
RUN mkdir -p /etc/nginx/conf.d
COPY nginx.conf /etc/nginx/conf.d
VOLUME /etc/nginx/conf.d


WORKDIR "/application"
VOLUME /application
