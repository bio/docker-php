FROM debian:buster-slim

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
  php7.4-cli \
  php7.4-bcmath \
  php7.4-curl \
  php7.4-json \
  php7.4-gd \
  php7.4-mailparse \
  php7.4-mbstring \
  php7.4-opcache \
  php7.4-pgsql \
  php7.4-readline \
  php7.4-xml \
  php7.4-xsl \
  php7.4-zip \
  && rm -r /var/lib/apt/lists/*

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --quiet --install-dir=/usr/local/bin/ --filename=composer
