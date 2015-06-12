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
RUN git clone https://github.com/mapbox/mapbox-studio.git ~/mapbox-studio
RUN cd ~/mapbox-studio && npm install


WORKDIR /root/mapbox-studio
# ENTRYPOINT ["./index.js"]
CMD ["./index.js"]
#CMD ["--host=*.*.*.*"]

EXPOSE 3000

# $> docker run -d -P --name tilestream feilunzhou/tilestream
# $> docer port tilestream
# $> boot2docker ip
#
# $> curl $BOOT2DOCKER_IP:$TILESTREAM_IP_MAPED
