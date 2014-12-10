From ubuntu_utopic_ssh:latest
MAINTAINER samsun <sam@ptthink.com>

RUN apt-get -y update --no-install-recommends
RUN apt-get -y install --no-install-recommends redis-server redis-tools pwgen
RUN apt-get -y clean

# supervisor setup
ADD redis_supervisord.conf /etc/supervisor/conf.d/redis_supervisord.conf

# Define mountable directories.
VOLUME ["/data"]

# Define working directory.
WORKDIR /data

# SET environment variables
ENV REDIS_TIMEOUT 0

EXPOSE 6379

CMD ["/usr/bin/supervisord","-n"]
