nmelectiondatr
==============

An R data package for Election Data in New Mexico
-------------------------------------------------

The package includes general election results for the state of New Mexico (2014, 2016 & 2018), including returns for federal, legislative, and statewide offices. Election returns are made available at the precinct, county, and state legislative levels.

Data included in the package have been collated from excel files made available by the [New Mexico Secretary of State](http://www.sos.state.nm.us/Elections_Data/Past_Election_Results.aspx). Anyone who has dealt with NM SOS data knows they are challenging to work with. Here, we make these data available in simple, aggregated tables that enable more straightforward analyses.

A full code-through of the scraping & summary processes is available [here](https://github.com/jaytimm/nmelectiondatr/blob/master/data-raw/scrape_nmelect_data.Rmd). Code includes functions for gathering election returns that can be used for future statewide/state legislative/federal elections.

Installation
------------

``` r
library(devtools)
devtools::install_github("jaytimm/nmelectiondatr")
library(nmelectiondatr)
```

Usage
-----

### Election returns

The package contains four data tables; their contents are summarized in the table below.

| Table                   | Contents                        |
|:------------------------|:--------------------------------|
| nmel\_results\_summary  | An overview of election winners |
| nmel\_results\_precinct | Election returns by precinct    |
| nmel\_results\_district | Election returns by district    |
| nmel\_results\_county   | Election returns by county      |

An overview of election winners for ...

``` r
nmelectiondatr::nmel_results_summary %>% head()
## # A tibble: 6 x 8
##   Year  Type                 Type_Sub Candidate Party Votes Percent Winner
##   <chr> <chr>                <chr>    <chr>     <chr> <dbl>   <dbl> <chr> 
## 1 2018  State Representative 1        RODNEY D~ REP   8512.      1. Winner
## 2 2018  State Representative 10       G ANDRES~ DEM   4927.      1. Winner
## 3 2018  State Representative 11       JAVIER I~ DEM   9875.      1. Winner
## 4 2018  State Representative 12       PATRICIO~ DEM   4326.      1. Winner
## 5 2018  State Representative 13       PATRICIA~ DEM   4749.      1. Winner
## 6 2018  State Representative 14       MIGUEL P~ DEM   5370.      1. Winner
```

Tables can also be viewed as a [collection of CSVs](https://github.com/jaytimm/nmelectiondatr/tree/master/nmelection_tables/CSVs) or as individual tabs in a single [Excel file](https://github.com/jaytimm/nmelectiondatr/tree/master/nmelection_tables/excel).

### Shapefiles

``` r
data.frame(table = c('nm_counties', 'nm_places', 'nm_senate_districts', 'nm_house_districts', 'us_congress_districts'),
           desc = c('New Mexico counties', 'Census designated places in New Mexico', 'State Senate districts in New Mexico', 'State House districts in New Mexico', 'Congressional districts in New Mexico')) %>%
  knitr::kable()
```

| table                   | desc                                   |
|:------------------------|:---------------------------------------|
| nm\_counties            | New Mexico counties                    |
| nm\_places              | Census designated places in New Mexico |
| nm\_senate\_districts   | State Senate districts in New Mexico   |
| nm\_house\_districts    | State House districts in New Mexico    |
| us\_congress\_districts | Congressional districts in New Mexico  |
