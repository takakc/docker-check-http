FROM debian:9
MAINTAINER kankan
ARG username="kan"
ARG password="kankan"


RUN apt-get update && apt-get install -y \
  git \
  vim \
  locales \
  nginx \
  openssl

# 日本語設定
COPY ./setting/locale.gen /etc/
RUN locale-gen
COPY ./setting/bashrc /tmp/
RUN cat /tmp/bashrc >>~/.bashrc
RUN rm -f /tmp/bashrc
COPY setting/ssl.conf /etc/nginx/conf.d/

# .php or .html put this directory
RUN mkdir -p /var/www/html
