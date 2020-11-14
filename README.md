
<!-- README.md is generated from README.Rmd. Please edit that file -->

``` r
library(ggplot2)
```

## Img itself is fine

``` r
path <- system.file("f_multi.jpg", package = "imginv")
img <- magick::image_read(path)
img
```

<img src="man/figures/README-unnamed-chunk-3-1.png" width="100%" />

``` r
i <- grid::rasterGrob(img, interpolate = FALSE)
width <- 1350
height <- 1350
```

## Inverted (in vignette)

``` r
ggplot() +
  scale_y_reverse() +
  coord_fixed(xlim = c(0, width),
              ylim = c(0, height)) +
  annotation_custom(i, 0, width, -height, 0)
```

<img src="man/figures/README-unnamed-chunk-5-1.png" width="100%" />

## Upright

``` r
ggplot() +
  #scale_y_reverse() +
  coord_fixed(xlim = c(0, width),
              ylim = c(0, height)) +
  annotation_custom(i, 0, width, height, 0)
```

<img src="man/figures/README-unnamed-chunk-6-1.png" width="100%" />