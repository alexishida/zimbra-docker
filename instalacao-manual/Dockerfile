#################################################################
# Dockerfile to build Zimbra Collaboration 8.8.7 container images
# Based on Ubuntu 16.04
# Created by Alex Ishida
# https://readyspace.com.sg/how-to-install-zimbra-collaboration-8-8-on-ubuntu-16-04-lts/
# https://www.ostechnix.com/install-zimbra-collaboration-suite-ubuntu-14-04-lts/
#################################################################
FROM ubuntu:16.04
MAINTAINER Alex Ishida <alexishida@gmail.com>

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
  unzip \
  iputils-ping

# VOLUME ["/opt/zimbra"]

EXPOSE 22 25 465 587 110 143 993 995 80 443 8080 8443 7071

COPY start.sh /opt/start.sh

CMD ["/bin/bash", "/opt/start.sh"]