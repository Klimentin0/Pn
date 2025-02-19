FROM php:8.3.11-fpm

# Рабочая директория контейнера
WORKDIR /var/www

# Зависимости
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    zip \
    git \
    unzip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd pdo pdo_mysql

# Компоузер
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# копируем сам проект в контейнер
COPY . .

# права доступа
RUN chown -R www-data:www-data /var/www

# открываем ПОРТ
EXPOSE 9000
CMD ["php-fpm"]
