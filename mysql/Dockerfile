FROM mysql
MAINTAINER Lef Well <lef.well@gmail.com>

RUN usermod -u 1000 mysql && chown mysql.mysql /var/run/mysqld/



EXPOSE 3306
VOLUME ["/var/www/htdocs"]


#sh$ docker build -t lef/mysql /var/www/Env/Dockerfiles/mysql
#sh$ docker run -p 3306:3306 -it lef/mysql -e MYSQL_ROOT_PASSWORD=LefWell --name mysql
# Install MySQL-Client in host