FROM centos
MAINTAINER Lef Well <lef.well@gmail.com>


RUN rpm -ivh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm && \
    yum update -y && \
    yum groupinstall -y base &&\
    yum install -y vim && \
    yum install -y gcc gcc-c++ autoconf automake zlib zlib-devel openssl openssl-devel pcre pcre-devel && \
    yum install -y make cmake libxml2 libxml2-devel openssl-devel curl && \
    yum install nginx -y

# forward request and error logs to docker log collector
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

RUN mkdir -p /etc/nginx/conf.d
ADD nginx_conf/nginx.conf /etc/nginx/nginx.conf
ADD nginx_conf/conf.d/* /etc/nginx/conf.d/


RUN systemctl enable nginx.service
#RUN systemctl start nginx.service

VOLUME ["/var/www/htdocs"]

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]

#sh$ docker build -t lef/nginx /var/www/Env/Dockerfiles/nginx
# -d  daemon
# --rm   remove this container when exit
#sh$ docker run -p 80:80 -v /var/www/htdocs:/var/www/htdocs --name nginx --link php:php --volumes-from php -it lef/nginx -d
#sh$ docker ps
#sh$ docker stop nginx
#sh$ docker start nginx
#sh$ docker kill nginx
#sh$ docker rm nginx
#sh$ docker run -it lef/nginx /bin/bash