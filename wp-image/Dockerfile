FROM ubuntu:xenial

RUN apt update && \
    apt install -y apache2 && \
    apt install -y php libapache2-mod-php php-mcrypt php-mysql curl && \
    rm -rf /var/lib/apt/lists/* && \
    rm /var/www/html/index.html

RUN curl -s https://es.wordpress.org/latest-es_ES.tar.gz -o wp.tar.gz && \
    tar xC /var/www/html -f wp.tar.gz --strip 1 && \
    rm wp.tar.gz

EXPOSE 80


ENTRYPOINT ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
