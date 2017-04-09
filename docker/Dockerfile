FROM php:7.0.7-apache

# Enable mod_rewrite for apache
# RUN a2enmod rewrite

# update /etc/apt/sources.list
# RUN cat /etc/apt/sources.list
RUN echo "deb http://mirrors.aliyun.com/debian/ jessie main non-free contrib" > /etc/apt/sources.list \
    && echo "deb http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian/ jessie main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb http://mirrors.aliyun.com/debian-security/ jessie/updates main non-free contrib" >> /etc/apt/sources.list \
    && echo "deb-src http://mirrors.aliyun.com/debian-security/ jessie/updates main non-free contrib" >> /etc/apt/sources.list

# Install mysqli php extension
RUN apt-get update && apt-get install -y \
        libmysqlclient-dev \
    && docker-php-ext-install -j$(nproc) mysqli \
    && rm -rf /var/lib/apt/lists/*
