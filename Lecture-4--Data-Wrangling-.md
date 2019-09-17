Lecture 4 (Data Wrangling)
================
CJ Snyder
9/17/2019

## Loading in the dataset

``` r
## reads in litters dataset

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
```

## Alternative way to upload litters dataset

``` r
litters_data_i = read_csv(file = "./data/FAS_litters.csv",
  skip = 10, col_names = FALSE)
```

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_character(),
    ##   X2 = col_character(),
    ##   X3 = col_double(),
    ##   X4 = col_double(),
    ##   X5 = col_double(),
    ##   X6 = col_double(),
    ##   X7 = col_double(),
    ##   X8 = col_double()
    ## )

## Reading in pups dataset

``` r
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

## Column Parsing - to specify column variable types

``` r
litters_data = read_csv(
  file = "./data/FAS_litters.csv",
  col_types = cols(
    Group = col_character(),
    `Litter Number` = col_character(),
    `GD0 weight` = col_double(),
    `GD18 weight` = col_double(),
    `GD of Birth` = col_integer(),
    `Pups born alive` = col_integer(),
    `Pups dead @ birth` = col_integer(),
    `Pups survive` = col_integer()
  )
)
```

## Read in an Excel File

``` r
mlb11_data = 
  read_excel(
    path = "./data/mlb11.xlsx", 
    n_max=20
  )
```

## Read in SAS

``` r
pulse_data = haven::read_sas("./data/public_pulse_data.sas7bdat")

## haven::read_sas -> taking the function read_sas out of 'haven' library
```
