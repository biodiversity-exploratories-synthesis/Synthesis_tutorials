Combine multiple plots on one panel
================
N. Schenk
2022-04-12

I am personally a big fan of the `cowplot::plot_grid()` function to
combine multiple plots on one panel, labelling them e.g. with letters A,
B, C. The plots just look publication ready!

However, `cowplot::plot_grid()` requires `ggplot` objects as inputs, and
is therefore not compatible with plots generated from packages not using
ggplot2.

This does not mean that R base can not do the job! R base is so
versatile, just needs some special attention to the details. Below you
find example code.

``` r
# use par() to arrange multiple plots together. Here, it is 4 plots (2 rows and 2 columns)
par(mfrow = c(2, 2)) 
# add the plot itself
plot(rnorm(10), rnorm(10))
# add the Label on top left
mtext("A", 2, adj=1, line=2, las = 1, padj = -4, font = 2)
# Note : probably you have to play around with the padj parameter. You could e.g. first try -4 as here,
# and if you don't see the label, try 0 and then adjust.

# add the other 3 plots : 
plot(rnorm(10), rnorm(10))
mtext("B", 2, adj=1, line=2, las = 1, padj = -4, font = 2)
plot(rnorm(10), rnorm(10))
mtext("C", 2, adj=1, line=2, las = 1, padj = -4, font = 2)
plot(rnorm(10), rnorm(10))
mtext("D", 2, adj=1, line=2, las = 1, padj = -4, font = 2)
```

![](combine_multiple_Rplots_on_one_panel_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->
