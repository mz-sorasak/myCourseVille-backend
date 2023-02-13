# Dev Usage, run from .docker/ directory:
# docker-compose build
# docker-compose run

FROM webdevops/php:8.1

RUN ln -sf /usr/share/zoneinfo/Asia/Bangkok /etc/localtime

ENV FPM_PM_MAX_CHILDREN=10 \
    FPM_PM_START_SERVERS=3 \
    FPM_PM_MIN_SPARE_SERVERS=2 \
    FPM_PM_MAX_SPARE_SERVERS=5 \
    FPM_MAX_REQUESTS=100

# # install GD and mcrypt
# RUN apt-get update && apt-get install -y \
#         libfreetype6-dev \
#         libjpeg62-turbo-dev \
#         libmcrypt-dev \
#         libpng12-dev \
#     && docker-php-ext-install -j$(nproc) iconv mcrypt \
#     && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
#     && docker-php-ext-install -j$(nproc) gd

#install Imagemagick & PHP Imagick ext
RUN apt-get update && apt-get install -y \
        libmagickwand-dev --no-install-recommends
# RUN pecl install imagick && docker-php-ext-enable imagick
