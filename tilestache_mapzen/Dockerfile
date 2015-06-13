# version: 0.1
# 

FROM python:2.7.10
MAINTAINER feilunzhou "feilunzhou@126.com"
ENV BUILD_DATE 2015-06-13


# prepare tools
RUN apt-get update
RUN apt-get install -yqq software-properties-common
RUN add-apt-repository -y ppa:mapnik/nightly-2.3
RUN apt-get update -ym
RUN apt-get install -yqq git


# install tilestache prerequesites
RUN apt-get install -yqqm libmapnik mapnik-utils python-mapnik build-essential autoconf libtool pkg-config python-opengl python-imaging python-pyrex python-pyside.qtopengl idle-python2.7 qt4-dev-tools qt4-designer libqtgui4 libqtcore4 libqt4-xml libqt4-test libqt4-script libqt4-network libqt4-dbus python-qt4 python-qt4-gl libgle3 python-dev zlib1g-dev libjpeg-dev python-psycopg2
RUN pip install modestmaps simplejson werkzeug pillow mapnik shapely protobuf mapbox_vector_tile


# install tilestream components
RUN git clone https://github.com/TileStache/TileStache.git ~/tilestache
RUN cd ~/tilestache && python setup.py install


WORKDIR /root/tilestache
# ENTRYPOINT ["./index.js", "start"]
CMD ["python", "./scripts/tilestache-server.py"]

EXPOSE 8080

# $> docker run -d -P --name tilestream feilunzhou/tilestream
# $> docer port tilestream
# $> boot2docker ip
#
# $> curl $BOOT2DOCKER_IP:$TILESTREAM_IP_MAPED
