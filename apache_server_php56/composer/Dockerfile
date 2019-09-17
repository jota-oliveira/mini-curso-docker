FROM ubuntu:18.04

ARG user="seu_usuario"
ARG group="www-data"

RUN apt-get update && apt-get install -y --no-install-recommends apt-utils && \
	apt-get upgrade -y && \
	apt-get install -y apt-transport-https ca-certificates curl software-properties-common gpg wget && \
	wget -q https://packages.sury.org/php/apt.gpg -O- | apt-key add - && \
	echo "deb https://packages.sury.org/php/ stretch main" | tee /etc/apt/sources.list.d/php.list

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y libcurl3 php5.6 libapache2-mod-php5.6 \
 	php5.6-mysql php5.6-common php5.6-cli php5.6-common php5.6-json php5.6-opcache php5.6-readline php5.6-mbstring php5.6-curl php5.6-xml zip unzip php5.6-zip composer

COPY ./entrypoint /usr/bin/
RUN chmod +x /usr/bin/entrypoint && mkdir /app

RUN getent group ${group} || groupadd ${group}
RUN useradd -ms /bin/bash ${user} && chown ${user} -R /app && chgrp -R ${group} /app && chmod 775 -R /app

CMD ["entrypoint"]
USER ${user}


