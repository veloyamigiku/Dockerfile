FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Tokyo
SHELL ["/bin/bash", "-c"]
RUN apt-get update
RUN apt-get install -y locales language-pack-ja tzdata software-properties-common
RUN add-apt-repository -y ppa:ethereum/ethereum
RUN apt-get update
RUN apt-get install -y ethereum solc
RUN localedef -f UTF-8 -i en_US en_US
RUN localedef -f UTF-8 -i ja_JP ja_JP
RUN sed -i '1iexport LANG="ja_JP.UTF-8"' ~/.profile
RUN sed -i '2iexport LC_ALL="ja_JP.UTF-8"' ~/.profile
