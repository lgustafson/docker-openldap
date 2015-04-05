FROM phusion/baseimage:0.9.16
MAINTAINER Leif Gustafson <lgustafson@gci.com>

ENV HOME /root

CMD ["/sbin/my_init"]

ADD ltb-project.list /etc/apt/sources.list.d/

RUN curl http://ltb-project.org/wiki/lib/RPM-GPG-KEY-LTB-project | \
    apt-key add - && \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install openldap-ltb \
      openldap-ltb-dbg openldap-ltb-check-password \
      openldap-ltb-contrib-overlays openldap-ltb-mdb-utils && \
    apt-get clean

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
