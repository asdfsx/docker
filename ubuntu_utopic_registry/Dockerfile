From ubuntu_utopic_ssh:latest
MAINTAINER samsun <sam@ptthink.com>

# Update
#RUN apt-get update \
# Install pip
#    && apt-get install -y \
RUN apt-get install -y \
        python-pip \
# Install deps for backports.lmza (python2 requires it)
        python-dev \
        liblzma-dev \
        libevent1-dev \
        git
    && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/docker/docker-registry.git -b 0.9.0 /docker-registry
RUN cp /docker-registry/config/boto.cfg /etc/boto.cfg

# Install core
RUN pip install /docker-registry/depends/docker-registry-core

# Install registry
RUN pip install file:///docker-registry#egg=docker-registry[bugsnag,newrelic,cors]

RUN patch \
 $(python -c 'import boto; import os; print os.path.dirname(boto.__file__)')/connection.py \
 < /docker-registry/contrib/boto_header_patch.diff

ENV DOCKER_REGISTRY_CONFIG /docker-registry/config/config_sample.yml
ENV SETTINGS_FLAVOR dev

# supervisor setup
ADD registry_supervisord.conf /etc/supervisor/conf.d/registry_supervisord.conf

VOLUME ["/registry"]

EXPOSE 5000

# supervisor to rule them all
CMD ["/usr/bin/supervisord","-n"]