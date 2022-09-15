Simple document
================

``` r
## echo=code, eval=running code, message=result
## naming chunk as chunk_library
## Control+Alt+I
## load packages at the very beginning of the rmd.
library(tidyverse)
```

I’m an R Markdown document!
<!-- not recommended including comments in a r markdown. -->

# Section 1

Here’s a **code chunk** that samples from a *normal distribution*:

``` r
samp = rnorm(100)
length(samp)
```

    ## [1] 100

# Section 2

I can take the mean of the sample, too! The mean is -0.113.

# Section 3

This is going to make a plot! First I generate a dataframe, then use
`ggplot` to make a scatterplot.

``` r
plot_df =
  tibble(
    x = rnorm(n = 1000),
    y = 1 + 2*x + rnorm(n = 1000)
  )

ggplot(plot_df, aes(x=x,y=y))+geom_point()
```

![](template_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

## Learning Assessment

``` r
la_df = tibble(
  norm_samp = rnorm(500, mean = 1),
  norm_samp_pos = norm_samp > 0,
  abs_norm_samp = abs(norm_samp)
)

ggplot(la_df, aes(x = abs_norm_samp)) + geom_histogram()
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](template_files/figure-gfm/chunk_assessment-1.png)<!-- -->
