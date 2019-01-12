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

**An overview of election winners** for ...

``` r
nmelectiondatr::nmel_results_summary
## # A tibble: 449 x 8
##    Year  Type         Type_Sub Candidate        Party Votes Percent Winner
##    <chr> <chr>        <chr>    <chr>            <chr> <dbl>   <dbl> <chr> 
##  1 2018  State Repre~ 1        RODNEY D MONTOYA REP   8512.   1.00  Winner
##  2 2018  State Repre~ 10       G ANDRES ROMERO  DEM   4927.   1.00  Winner
##  3 2018  State Repre~ 11       JAVIER I MARTIN~ DEM   9875.   1.00  Winner
##  4 2018  State Repre~ 12       PATRICIO R RUIL~ DEM   4326.   1.00  Winner
##  5 2018  State Repre~ 13       PATRICIA A ROYB~ DEM   4749.   1.00  Winner
##  6 2018  State Repre~ 14       MIGUEL P GARCIA  DEM   5370.   1.00  Winner
##  7 2018  State Repre~ 15       DAYAN M HOCHMAN  DEM   6583.   0.521 Winner
##  8 2018  State Repre~ 15       BRAD WINTER      REP   6043.   0.479 ""    
##  9 2018  State Repre~ 16       ANTONIO 'MOE' M~ DEM   7694.   1.00  Winner
## 10 2018  State Repre~ 17       DEBORAH A ARMST~ DEM   7027.   0.650 Winner
## # ... with 439 more rows
```

**Election returns by precinct** ...

``` r
nmelectiondatr::nmel_results_precinct
## # A tibble: 107,965 x 8
##    Year  Type     Type_Sub County_Name Precinct_Num Candidate  Votes Party
##    <chr> <chr>    <chr>    <chr>              <dbl> <chr>      <dbl> <chr>
##  1 2018  State R~ 1        San Juan             28. RODNEY D ~  284. REP  
##  2 2018  State R~ 1        San Juan             29. RODNEY D ~  197. REP  
##  3 2018  State R~ 1        San Juan             31. RODNEY D ~  815. REP  
##  4 2018  State R~ 1        San Juan             32. RODNEY D ~  129. REP  
##  5 2018  State R~ 1        San Juan             33. RODNEY D ~  283. REP  
##  6 2018  State R~ 1        San Juan             34. RODNEY D ~  241. REP  
##  7 2018  State R~ 1        San Juan             39. RODNEY D ~  717. REP  
##  8 2018  State R~ 1        San Juan             41. RODNEY D ~  627. REP  
##  9 2018  State R~ 1        San Juan             42. RODNEY D ~  555. REP  
## 10 2018  State R~ 1        San Juan             44. RODNEY D ~  621. REP  
## # ... with 107,955 more rows
```

**Election returns by county** ... which additionally include ...

``` r
nmelectiondatr::nmel_results_county
## # A tibble: 8,024 x 7
##    Year  Type                  NAME       Candidate  Votes Party Cast 
##    <chr> <chr>                 <chr>      <chr>      <dbl> <chr> <chr>
##  1 2018  United States Senator Bernalillo MICK RICH 61932. REP   Total
##  2 2018  United States Senator Catron     MICK RICH  1075. REP   Total
##  3 2018  United States Senator Chaves     MICK RICH  8727. REP   Total
##  4 2018  United States Senator Cibola     MICK RICH  1842. REP   Total
##  5 2018  United States Senator Colfax     MICK RICH  1615. REP   Total
##  6 2018  United States Senator Curry      MICK RICH  5896. REP   Total
##  7 2018  United States Senator De Baca    MICK RICH   342. REP   Total
##  8 2018  United States Senator Dona Ana   MICK RICH 18101. REP   Total
##  9 2018  United States Senator Eddy       MICK RICH  8826. REP   Total
## 10 2018  United States Senator Grant      MICK RICH  3598. REP   Total
## # ... with 8,014 more rows
```

**Election returns by state legislative districts** ... which additionally include ...

``` r
nmelectiondatr::nmel_results_district
## # A tibble: 1,476 x 7
##    Year  Type                 NAME  Candidate          Votes Party Cast   
##    <chr> <chr>                <chr> <chr>              <dbl> <chr> <chr>  
##  1 2018  State Representative 1     RODNEY D MONTOYA   8512. REP   Total  
##  2 2018  State Representative 1     RODNEY D MONTOYA    521. REP   Absent~
##  3 2018  State Representative 1     RODNEY D MONTOYA   4651. REP   Early  
##  4 2018  State Representative 1     RODNEY D MONTOYA   3340. REP   Electi~
##  5 2018  State Representative 2     JAMES RJ STRICKLER 5437. REP   Total  
##  6 2018  State Representative 2     JAMES RJ STRICKLER  318. REP   Absent~
##  7 2018  State Representative 2     JAMES RJ STRICKLER 2833. REP   Early  
##  8 2018  State Representative 2     JAMES RJ STRICKLER 2286. REP   Electi~
##  9 2018  State Representative 3     MARY P SCHILDMEYER 1817. DEM   Total  
## 10 2018  State Representative 3     MARY P SCHILDMEYER  116. DEM   Absent~
## # ... with 1,466 more rows
```

Tables can also be viewed as a [collection of CSVs](https://github.com/jaytimm/nmelectiondatr/tree/master/nmelection_tables/CSVs) or as individual tabs in a single [Excel file](https://github.com/jaytimm/nmelectiondatr/tree/master/nmelection_tables/excel).

### Shapefiles

| table                   | desc                                   |
|:------------------------|:---------------------------------------|
| nm\_counties            | New Mexico counties                    |
| nm\_places              | Census designated places in New Mexico |
| nm\_senate\_districts   | State Senate districts in New Mexico   |
| nm\_house\_districts    | State House districts in New Mexico    |
| us\_congress\_districts | Congressional districts in New Mexico  |
