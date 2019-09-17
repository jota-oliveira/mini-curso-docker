FROM ubuntu:18.04
ARG user="koder"
#COPY ./entrypoint /usr/bin/

RUN apt update && apt upgrade -y && apt install -y nodejs npm
#RUN chmod +x /usr/bin/entrypoint
RUN mkdir /app && useradd -ms /bin/bash ${user} && chown ${user} -R /app && chmod 775 -R /app

WORKDIR /app
USER ${user}