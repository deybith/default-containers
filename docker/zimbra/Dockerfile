FROM ubuntu:16.04

RUN echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install \
  wget \
  dialog \
  openssh-client \
  software-properties-common \
  dnsmasq \
  dnsutils \
  net-tools \
  sudo \
  rsyslog \
  unzip

VOLUME ["/opt/zimbra"]

COPY ./docker/zimbra/opt /opt/

COPY ./docker/zimbra/etc /etc/

CMD ["/bin/bash", "/opt/start.sh", "-d"]
