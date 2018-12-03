nmelectiondatr
==============

An R data package containing general election results for the state of New Mexico (2014+)
-----------------------------------------------------------------------------------------

This package provides access to data about the 53rd New Mexico State Legislature, including roll call data, bill details, state legislator information, and some high-level characterizations of legislator voting patterns.

Data included in the package have been scraped from thousands of PDFs made available via the official site of the [New Mexico State Legislature](https://www.nmlegis.gov/Legislation/Legislation_List). A full code-through of the scraping & summary processes is available [here](https://github.com/jaytimm/nmlegisdatr/blob/master/data-raw/scrape_nmsl_data.md).

A companion package to `nmlegisdatr`.

Installation
------------

``` r
library(devtools)
devtools::install_github("jaytimm/nmelectiondatr")
library(nmelectiondatr)
```

Usage
-----

The package contains six data tables; their contents are summarized in the table below.

| Table                  | Contents                                                                               |
|:-----------------------|:---------------------------------------------------------------------------------------|
| nml\_legislation       | All introduced legislation, including bill id, title, and bill description             |
| nml\_legislators       | All legislators in both chambers, including party affiliation and legislative district |
| nml\_rollcall          | Roll calls for all legislation reaching either chamber for vote                        |
| nml\_sponsors          | Sponsors for each bill                                                                 |
| nml\_rollcall\_results | Roll call results, including results disaggregated by political affiliation            |
| nml\_legislator\_descs | Votes cast, atttendance rates, and party loyalty rates for all legislators             |

Tables can also be viewed as a [collection of CSVs](https://github.com/jaytimm/nmlegisdatr/tree/master/nmsl_tables/CSVs) or as individual tabs in a single [Excel file](https://github.com/jaytimm/nmlegisdatr/tree/master/nmsl_tables/excel).
