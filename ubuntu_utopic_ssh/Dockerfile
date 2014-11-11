From ubuntu:utopic
MAINTAINER samsun <sam@ptthink.com>

RUN apt-get update
RUN apt-get -y install openssh-server supervisor

# Setup sshd environement
RUN mkdir /var/run/sshd
RUN chmod 755 /var/run/sshd

RUN sed -ri 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
RUN sed -ri 's/PermitRootLogin without-password/PermitRootLogin yes/g' /etc/ssh/sshd_config
RUN echo 'root:123456' | chpasswd

# supervisor setup
ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

VOLUME /var/log

EXPOSE 22

# supervisor to rule them all
CMD ["/usr/bin/supervisord","-n"]

