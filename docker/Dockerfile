#################################################################
# Dockerfile to build Zimbra Collaboration 8.8.7 container images
# Based on Ubuntu 16.04
# Created by Alex Ishida
#################################################################
FROM ubuntu:16.04
MAINTAINER Alex Ishida <alexishida@gmail.com>

RUN echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

RUN apt-get update && apt-get -y upgrade && apt-get -y autoremove

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install \
  wget \
  dialog \
  openssh-client \
  openssh-server \
  software-properties-common \
  dnsmasq \
  dnsutils \
  net-tools \
  sudo \
  nano \
  rsyslog \
  unzip

VOLUME ["/opt/zimbra"]

EXPOSE 22 25 465 587 110 143 993 995 80 443 8080 8443 7071

COPY opt /opt/

COPY etc /etc/

CMD ["/bin/bash", "/opt/start.sh", "-d"]
