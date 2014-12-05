From ubuntu_utopic_ssh:latest
MAINTAINER samsun <sam@ptthink.com>

RUN apt-get -y update --no-install-recommends
RUN apt-get -y install --no-install-recommends python-pip 
RUN apt-get -y clean

RUN pip install pypiserver
RUN pip install passlib

# supervisor setup
ADD pypi_supervisord.conf /etc/supervisor/conf.d/pypi_supervisord.conf

ADD htaccess /root/pypiserver/htaccess

# Define mountable directories.
VOLUME ["/data/pypiserver/packages"]

# Define working directory.
WORKDIR /data/pypiserver/packages

EXPOSE 8080

CMD ["/usr/bin/supervisord","-n"]