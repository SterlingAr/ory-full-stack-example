FROM php:7.2-cli-stretch

ADD install-composer.sh /usr/bin/install-composer.sh

RUN apt-get update --yes \
    && apt-get install --yes git wget  zlib1g-dev libzip-dev unzip \
    && docker-php-ext-install zip

RUN chmod +x /usr/bin/install-composer.sh \
    && install-composer.sh \
    && git clone https://github.com/SterlingAr/openid-user-manager /root/php-app && ls -la /root


WORKDIR /root/php-app

RUN cp .env.dist .env && composer install

ADD php.ini "$PHP_INI_DIR/php.ini"
#RUN cp $PHP_INI_DIR/php.ini-production $PHP_INI_DIR/php.ini  \
#    && sed -i 's/variables_order = "GPCS" /variables_order = "EGPCS"/' "$PHP_INI_DIR/php.ini"

EXPOSE 8000
