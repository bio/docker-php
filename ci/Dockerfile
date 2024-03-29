FROM debian:bookworm-slim

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
  php8.0-cli \
  php8.0-bcmath \
  php8.0-curl \
  php8.0-gd \
  php8.0-mailparse \
  php8.0-mbstring \
  php8.0-opcache \
  php8.0-pgsql \
  php8.0-readline \
  php8.0-xml \
  php8.0-xsl \
  php8.0-zip \
  && rm -r /var/lib/apt/lists/*

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --quiet --install-dir=/usr/local/bin/ --filename=composer
