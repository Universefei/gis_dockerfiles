# version: 0.1
# 

FROM ubuntu:14.04
MAINTAINER feilunzhou "feilunzhou@126.com"
ENV BUILD_DATE 2015-06-12


# prepare tools
RUN apt-get update
RUN apt-get install -yqq git curl


# install node.js v0.10.33
RUN curl -sL https://deb.nodesource.com/setup | sudo bash -
RUN apt-get install -y nodejs


# install tilestream components
RUN git clone https://github.com/mapbox/tilemill.git ~/tilemill
RUN cd ~/tilemill && npm install


WORKDIR /root/tilemill
# ENTRYPOINT ["./index.js"]
CMD ["./index.js", " core"]

EXPOSE 20008
EXPOSE 20009

# $> docker run -d -P --name tilemill feilunzhou/tilemill
# $> docer port tilestream
# $> boot2docker ip
#
# $> curl $BOOT2DOCKER_IP:$TILESTREAM_IP_MAPED
