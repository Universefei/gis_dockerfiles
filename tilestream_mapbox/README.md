mapbox/tilestream
=================

TileStream is a high-performance map tile server powered by MBTiles.

It's like TileCache, TileStache, and other map servers in that it serves normal image files that can be used in OpenLayers, Google Maps, Modest Maps, and other Javascript APIs without much trouble - and with lots of enhancements when you use Mapbox.js.

It's not like those tile servers in that it doesn't yet generate maps, it only serves maps that are generated with TileMill. This means that it's reliably fast but not designed to serve live data.

MapBox Hosting uses the same internals as TileStream but adds many features and is a hosted service rather than an installable application.

[MapBox/tilestream Github Repo click here](https://github.com/mapbox/tilestream)


How to use this docker image?
-----------------------------

`docker run -d [-P] [-v] feilunzhou/tilestream [$OTHER_ARGS]`


Run the Server
--------------

```
docker run -d -P 8888:8888 \
           -v ${YOUR_MBTILE_DIR}:/root/Documents/MapBox/tiles \
           --name tilestream feilunzhou/tilestream
```


Embrace the tile service
------------------------

Open your favorite browser and visit: `http://localhost:8888` to enjoy tiles web interface!


