FROM php
MAINTAINER Lef Well <lef.well@gmail.com>

USER root


#RUN mkdir -p /var/www
ADD php.ini /usr/local/etc/php/php.ini
ADD php-fpm.conf /usr/local/etc/php-fpm.conf

ADD composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer



RUN useradd -s /sbin/nologin www

#RUN mkdir -p /var/www/htdocs
#RUN chown -R www:www /var/www/htdocs
#RUN chmod -R 777 /var/www/htdocs

WORKDIR  /var/www/htdocs
 
VOLUME ["/var/www/htdocs"]

USER www

ENTRYPOINT ["php", "-S", "0.0.0.0:9000"]
EXPOSE 9000


#sh$ docker build -t lef/php /var/www/Env/Dockerfiles/php
# -d  daemon
# --rm   remove this container when exit
#sh$ docker run -p 9000:9000 -v /var/www/htdocs:/var/www/htdocs --name php -it lef/php
#sh$ docker ps
#sh$ docker stop php
#sh$ docker start php
#sh$ docker kill php
#sh$ docker run -it lef/php /bin/bash