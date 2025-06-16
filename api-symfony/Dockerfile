FROM php:8.2-apache

# Installer les dépendances système utiles (ex : extensions PHP pour Symfony + PostgreSQL)
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libpq-dev \
    libzip-dev \
    zip \
    && docker-php-ext-install pdo pdo_pgsql zip

# Installer Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Activer mod_rewrite pour Symfony
RUN a2enmod rewrite

# Configurer Apache pour que /public soit le root
COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf

# Travailler dans le bon dossier
WORKDIR /var/www/html

# Droits pour éviter les soucis
RUN chown -R www-data:www-data /var/www/html
