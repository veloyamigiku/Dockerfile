FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Tokyo
SHELL ["/bin/bash", "-c"]
RUN apt-get update
RUN apt-get install -y locales language-pack-ja git build-essential curl libssl-dev zlib1g-dev tzdata libsqlite3-dev sqlite3
RUN localedef -f UTF-8 -i en_US en_US
RUN localedef -f UTF-8 -i ja_JP ja_JP
RUN sed -i '1iexport LANG="ja_JP.UTF-8"' ~/.profile
RUN sed -i '2iexport LC_ALL="ja_JP.UTF-8"' ~/.profile
RUN git config --global core.autocrlf false
RUN git clone https://github.com/rbenv/rbenv.git ~/.rbenv
RUN cd ~/.rbenv && src/configure && make -C src
RUN sed -i '1iexport PATH="$HOME/.rbenv/bin:$PATH"' ~/.bashrc
ENV PATH="/root/.rbenv/bin:/root/.rbenv/shims:${PATH}"
RUN mkdir -p "$(rbenv root)"/plugins
RUN git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
RUN ls -ld "$(rbenv root)"/plugins/ruby-build
RUN echo 'eval "$(rbenv init - bash)"' >> ~/.bashrc
RUN source ~/.bashrc
RUN rbenv install 3.0.3 -v
RUN rbenv global 3.0.3
RUN gem install bundler
