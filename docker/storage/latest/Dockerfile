#++++++++++++++++++++++++++++++++++++++
# Storage Docker container
#++++++++++++++++++++++++++++++++++++++

FROM webdevops/base:latest
MAINTAINER info@webdevops.io
LABEL vendor=WebDevOps.io
LABEL io.webdevops.layout=6
LABEL io.webdevops.version=0.23.0

# Deploy scripts/configurations
COPY . /opt/docker/
RUN mkdir /storage/ \
    && chmod 777 /storage/ \
    && bash /opt/docker/bin/bootstrap.sh

VOLUME "/storage"

CMD ["noop"]
