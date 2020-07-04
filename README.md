# pbf2png
PBF(MVT) tiles to PNG convertor - [QtPBFImagePlugin](https://github.com/tumic0/QtPBFImagePlugin)
example/benchmark app. Converts a directory of Mapbox vector tiles to PNG tiles.

## Build
```shell
qmake pbf2png.pro
make
```

## Usage
```shell
pbf2png [options] DIR
```

Use `pbf2png -h` for help. The parameters should be self-explanatory, except the
`-M` - tile name mask parameter. It's only there because of the notoriously known
design flaw in the Mapbox vector tiles specification - the missing zoom level
in the tile data. To render a tile, a workaround that fetches the zoom level from
the file name (or somewhere else) is required. The default mask(regular expression)
is `([0-9]+).*` which should fit all common tile name schemes like `$z-$x-$y.pbf`,
`$z_$y_$x.mvt`, etc.

## Styles
See the QtPBFImagePlugin [documentation](https://github.com/tumic0/QtPBFImagePlugin#styles)
for how to set the style used for rendering the tiles. For the default OpenMapTiles
data schema and the default OSM-Liberty style nothing needs to be done.
