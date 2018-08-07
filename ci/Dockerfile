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
  php7.2-fpm \
  php7.2-apcu \
  php7.2-bcmath \
  php7.2-curl \
  php7.2-json \
  php7.2-gd \
  php7.2-mailparse \
  php7.2-mbstring \
  php7.2-opcache \
  php7.2-pgsql \
  php7.2-readline \
  php7.2-soap \
  php7.2-xml \
  php7.2-xsl \
  php7.2-zip \
  && rm -r /var/lib/apt/lists/*

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --quiet --install-dir=/usr/local/bin/ --filename=composer

