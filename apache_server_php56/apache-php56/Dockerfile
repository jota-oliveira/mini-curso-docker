FROM debian:jessie

RUN apt-get update && apt-get install -y --no-install-recommends apt-utils && \
	apt-get upgrade -y && \
	apt-get install -y curl software-properties-common apache2 apache2-utils wget \
	php5 php5 libapache2-mod-php5 php5-mysql php5-cli php5-common php5-json php5-readline

RUN echo "<Directory /var/www/>" >> /etc/sysctl.conf && \
	echo "Options Indexes FollowSymLinks" >> /etc/sysctl.conf && \
    echo "AllowOverride All" >> /etc/sysctl.conf && \
    echo "Require all granted" >> /etc/sysctl.conf && \
	echo "</Directory>" >> /etc/sysctl.conf && \
	rm /var/www/html/index.html && \
	a2enmod php5 && \
	sed -i -e 's/display_errors = Off/display_errors = On/g' /etc/php5/apache2/php.ini && \
	sed -i -e 's/display_startup_errors = Off/display_startup_errors = On/g' /etc/php5/apache2/php.ini && \
	sed -i -e 's/log_errors = Off/log_errors = On/g' /etc/php5/apache2/php.ini && \
	sed -i -e 's/track_errors = Off/track_errors = On/g' /etc/php5/apache2/php.ini  && \
	service apache2 start

WORKDIR /var/www/html
EXPOSE 80
CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]
