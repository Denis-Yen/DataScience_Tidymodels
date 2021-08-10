Precios De Los Muebles
================
Denis Rodríguez
2021-08-10

Vamos a predecir los precios de los muebles usando el dataset de
tidyTuesday.

## Explore data

``` r
library(tidyverse)
ikea = read.csv("https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-11-03/ikea.csv")
```

### Auditoria de datos

``` r
library(funModeling)
ikea %>%
  na.omit() %>%
  df_status()
```

    ##             variable q_zeros p_zeros q_na p_na q_inf p_inf    type unique
    ## 1                  X       0       0    0    0     0     0 integer   1899
    ## 2            item_id       0       0    0    0     0     0 integer   1602
    ## 3               name       0       0    0    0     0     0  factor    289
    ## 4           category       0       0    0    0     0     0  factor     17
    ## 5              price       0       0    0    0     0     0 numeric    729
    ## 6          old_price       0       0    0    0     0     0  factor    248
    ## 7    sellable_online       0       0    0    0     0     0  factor      2
    ## 8               link       0       0    0    0     0     0  factor   1602
    ## 9       other_colors       0       0    0    0     0     0  factor      2
    ## 10 short_description       0       0    0    0     0     0  factor    992
    ## 11          designer       0       0    0    0     0     0  factor    191
    ## 12             depth       0       0    0    0     0     0 integer    108
    ## 13            height       0       0    0    0     0     0 integer    178
    ## 14             width       0       0    0    0     0     0 integer    241

cómo se relaciona el precio con otras dimensiones de los muebles?
![](ArbolesDescicion_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

## Build a model
