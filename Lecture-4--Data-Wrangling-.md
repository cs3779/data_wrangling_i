Lecture 4 (Data Wrangling)
================
CJ Snyder
9/17/2019

## Loading in the dataset

``` r
## reads in a dataset

litters_data = read_csv(file="./data/FAS_litters.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   Group = col_character(),
    ##   `Litter Number` = col_character(),
    ##   `GD0 weight` = col_double(),
    ##   `GD18 weight` = col_double(),
    ##   `GD of Birth` = col_double(),
    ##   `Pups born alive` = col_double(),
    ##   `Pups dead @ birth` = col_double(),
    ##   `Pups survive` = col_double()
    ## )

``` r
litters_data = janitor::clean_names(litters_data)

pups_data = read_csv(file = "./data/FAS_pups.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   `Litter Number` = col_character(),
    ##   Sex = col_double(),
    ##   `PD ears` = col_double(),
    ##   `PD eyes` = col_double(),
    ##   `PD pivot` = col_double(),
    ##   `PD walk` = col_double()
    ## )

``` r
## Absolute way to upload dataset -> pups_data = read_csv(file = "C:/Users/csnyd/Documents/School Documents/Fall Semester - 2019/Data Science/Lecture 4/data_wrangling_i/data/FAS_pups.csv")

pups_data = janitor::clean_names(pups_data)
```
