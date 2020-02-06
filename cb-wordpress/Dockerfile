FROM debian:stretch-slim

ENV     DEBIAN_FRONTEND noninteractive

RUN     set -exu; \
        apt update -y; \
        apt install -y php-mysql php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip apache2 wget libapache2-mod-php; \
        cd /var/www/; \
        wget -O- https://wordpress.org/latest.tar.gz | tar zx ; \
        rm -fr /var/www/html; \
        mv wordpress html; \ 
        a2enmod rewrite ; \
        a2dismod status

RUN     set -exu; \
        ln -sfT /dev/stdout /var/log/apache2/access.log ; \
        ln -sfT /dev/stderr /var/log/apache2/error.log ;

EXPOSE 80

CMD ["apache2ctl","-D","FOREGROUND"]