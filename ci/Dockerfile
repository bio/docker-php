FROM debian:stretch

RUN apt-get update && apt-get install -y \
  apt-transport-https \
  lsb-release \
  ca-certificates \
  curl \
  git \
  netcat-openbsd
RUN curl -sS https://packages.sury.org/php/apt.gpg -o /etc/apt/trusted.gpg.d/php.gpg
RUN touch /etc/apt/sources.list.d/php.list
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list

RUN apt-get update && apt-get install -y --no-install-recommends \
  php7.1-fpm \
  php7.1-apcu \
  php7.1-bcmath \
  php7.1-curl \
  php7.1-json \
  php7.1-gd \
  php7.1-mailparse \
  php7.1-mbstring \
  php7.1-mcrypt \
  php7.1-opcache \
  php7.1-pgsql \
  php7.1-readline \
  php7.1-soap \
  php7.1-xml \
  php7.1-xsl \
  php7.1-zip \
  && rm -r /var/lib/apt/lists/*

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --quiet --install-dir=/usr/local/bin/ --filename=composer

