# cfgeo-vendorlibs
geospatial vendor libraries for Pivotal Cloud Foundry

### includes

| Library | Version |
| ------- | ------- |
| LCMS | 2.8 |
| GDAL | 2.1.2 |
| GEOS | 3.6.0 |
| HDF5 | 1.8.18 |
| LIBKML | 1.3.0 |
| NETCDF | 4.4.1.1 |
| OPENJPEG | 2.1 |
| POSTGRESQL CLIENT | 9.6.1 |
| PROJ4 | 4.9.3 |

__\+ dependencies__


## build steps
_Note: build requires docker to build the vendorlibs!_

+  run the following command:
```
docker run -v $PWD:/build -it cloudfoundry/cflinuxfs2:1.46.0 /build/build.sh
```
This will result in a archive "cfgeo-vendorlibs.\*.cflinuxfs2.x86_64.tar.gz" being
created in the root of the repo directory.

## usage steps

+ add the archive "cfgeo-vendorlibs._version-number_.cflinuxfs2.x86_64.tar.gz" to the `$REPO_ROOT/cf/vendor` of your app you will push to cf.
+ use `https://github.com/BerryDaniel/python-buildpack#v1.5.13_vendor` for the `buildpack:` entry in your manifest.yml
+ push your app to cloudfoundry
