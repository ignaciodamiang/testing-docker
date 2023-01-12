FROM ubuntu:22.04
LABEL maintainer="Ignacio Damián González" mail="ignaciodamiang@gmail.com"

ENV CONTAINER_TIMEZONE="America/Argentina/Buenos_Aires"
RUN ln -snf /usr/share/zoneinfo/$CONTAINER_TIMEZONE /etc/localtime && echo $CONTAINER_TIMEZONE > /etc/timezone

RUN apt update && apt install -y apache2 apache2-utils
RUN apt clean

RUN echo 'Hello, docker' > /var/www/index.html

EXPOSE 80

ENTRYPOINT ["/usr/sbin/apache2"]
CMD ["-D", "FOREGROUND"]