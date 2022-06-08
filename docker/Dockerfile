FROM wordpress:php8.0-apache
 
# Install xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug
 
# Install Less for WP-CLI
RUN apt-get update && apt-get -y install less
 
# Install WP-CLI
RUN curl -s -o /usr/local/bin/wp \
    https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
    && chmod +x /usr/local/bin/wp

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Node
RUN curl -sL https://deb.nodesource.com/setup_16.x  | bash -
RUN apt-get -y install nodejs
# RUN npm install