FROM ubuntu:18.04

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y libcurl4 php7.2 php7.2-mysql tzdata \
	php7.2-common php7.2-cli php7.2-common php7.2-json php7.2-opcache php7.2-readline \
	php7.2-mbstring php7.2-curl php7.2-xml zip unzip php7.2-zip composer

COPY ./entrypoint /usr/bin/
RUN chmod +x /usr/bin/entrypoint && mkdir /app
RUN getent group ${group} || groupadd ${group}

ARG user="koder"
ARG group="www-data"

RUN useradd -m -s /bin/bash ${user} && chown ${user} -R /app && chgrp -R ${group} /app && chmod 775 -R /app

#ENTRYPOINT ["entrypoint.sh"]
CMD ["entrypoint", ""]
USER ${user}


