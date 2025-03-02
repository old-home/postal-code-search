FROM php:8.4-fpm
RUN apt-get update \
    && apt-get install -y \
    git \
    zip \
    unzip \
    vim \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    libfontconfig1 \
    libxrender1 && \
    docker-etc-ext-configure gd --with-freetype --with-jpeg && \
    docker-etc-ext-install gd bcmath pdo_mysql exif && \
    pecl install redis
COPY --from=composer /usr/bin/composer /usr/bin/composer

WORKDIR /src
ADD . /src/storage
RUN chown -R www-data:www-data /src/storage
EXPOSE 9000
