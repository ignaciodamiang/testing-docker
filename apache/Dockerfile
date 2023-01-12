FROM ubuntu:22.04
LABEL maintainer="Ignacio Damián González" mail="ignaciodamiang@gmail.com"

ENV CONTAINER_TIMEZONE="America/Argentina/Buenos_Aires"
RUN ln -snf /usr/share/zoneinfo/$CONTAINER_TIMEZONE /etc/localtime && echo $CONTAINER_TIMEZONE > /etc/timezone

RUN apt update && apt install -y apache2 apache2-doc
RUN apt clean

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_RUN_DIR /var/www/html

RUN echo 'Hello, docker' > /var/www/html/index.html

EXPOSE 80

ENTRYPOINT ["/usr/sbin/apache2"]
CMD ["-D", "FOREGROUND"]