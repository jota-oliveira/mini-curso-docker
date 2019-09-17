FROM ubuntu:18.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
        apache2 php7.2 libcurl4 libapache2-mod-php7.2 php7.2-mysql php-common php7.2-cli php7.2-common php7.2-json php7.2-opcache php7.2-readline

RUN echo "<Directory /var/www/>" >> /etc/sysctl.conf && \
    echo "Options Indexes FollowSymLinks" >> /etc/sysctl.conf && \
    echo "AllowOverride All" >> /etc/sysctl.conf && \
    echo "Require all granted" >> /etc/sysctl.conf && \
    echo "</Directory>" >> /etc/sysctl.conf && \
	rm /var/www/html/index.html && \
	a2enmod php7.2 && \
	sed -i -e 's/display_errors = Off/display_errors = On/g' /etc/php/7.2/apache2/php.ini && \
	sed -i -e 's/display_startup_errors = Off/display_startup_errors = On/g' /etc/php/7.2/apache2/php.ini && \
	sed -i -e 's/log_errors = Off/log_errors = On/g' /etc/php/7.2/apache2/php.ini && \
	sed -i -e 's/track_errors = Off/track_errors = On/g' /etc/php/7.2/apache2/php.ini  && \
	service apache2 start

WORKDIR /var/www/html
EXPOSE 80
CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
