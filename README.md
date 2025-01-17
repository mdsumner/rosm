ROSM: Open Street Map tiles in R
================

<!-- README.md is generated from README.Rmd. Please edit that file -->
<!-- badges: start -->

[![Codecov test
coverage](https://codecov.io/gh/paleolimbot/rosm/branch/master/graph/badge.svg)](https://app.codecov.io/gh/paleolimbot/rosm?branch=master)
<!-- badges: end -->

Download and plot [Open Street Map](https://www.openstreetmap.org/),
[Bing Maps](https://www.bing.com/maps), and other tiled map sources. Use
to create high-resolution basemaps and add hillshade to vector based
maps. Note that rosm uses base plotting and not ggplot2: for mapping in
ggplot2, use
[ggspatial](https://github.com/paleolimbot/ggspatial)::annotation_map_tile().

## Installation

The **rosm** package is [available on
CRAN](https://cran.r-project.org/package=rosm), and can be installed
using `install.packages("rosm")`.

## Example

``` r
library(prettymapr)
library(rosm)

# specify a bounding box
altalake <- makebbox(50.1232, -122.9574, 50.1035, -123.0042)
prettymap(
  {
    # plot tiles (see also osm.raster() and bmaps.plot())
    osm.plot(altalake)
    osm.points(c(-122.9841, -122.9812), c(50.11055, 50.11765),
      pch = 15, cex = 0.6, col = "white"
    )
    osm.text(c(-122.9841, -122.9812), c(50.11055, 50.11765),
      labels = c("GC6", "GC2"), adj = c(-0.2, 0.5), cex = 0.7, col = "white"
    )
  },
  scale.label.col = "white"
)
```

<img src="man/figures/README-example-1.png" width="100%" />

## The Future?

Some other great projects have popped up in the last few years, such
that **rosm** will probably be retired in the next year. Packages that
depend on will continue to work, but it is likely that a new API will
pop up under a different name.
