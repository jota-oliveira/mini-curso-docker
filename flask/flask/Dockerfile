FROM ubuntu:18.04

RUN apt update && apt install -y python3 python3-pip
RUN pip3 install flask flask-restful
RUN mkdir app

WORKDIR /app
EXPOSE 5000
EXPOSE 80