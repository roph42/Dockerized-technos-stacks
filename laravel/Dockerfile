FROM php:8.2-fpm
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    nginx
RUN apt-get clean && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
WORKDIR /var/www
COPY . /var/www
COPY --chown=www-data:www-data . /var/www
RUN composer install
RUN chown -R www-data:www-data /var/www
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD service nginx start && php-fpm
