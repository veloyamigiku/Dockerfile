FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Tokyo
RUN apt-get update
RUN apt-get install -y npm wget
RUN npm install -g n
RUN apt purge nodejs npm -y

