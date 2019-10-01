--- 
title: "Causal Inference Book: Exercises -- R code"
author: "Book by M. A. Hernán and J. M. Robins, R code by Joy Shi and Roger Logan, R Markdown code and tweaks by Tom Palmer"
date: "2019-10-01"
site: bookdown::bookdown_site
documentclass: book
#bibliography: [book.bib, packages.bib]
#biblio-style: apalike
link-citations: yes
description: "Code examples from the Causal Inference Book by M. A. Hernán and J. M. Robins https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/"
geometry: margin=1in
fontsize: 10pt
linestretch: 1.1
---



# Preface{-}

This book presents code examples from the Causal Inference Book by Hernán and Robins, which is available in draft form from the following webpage.

https://www.hsph.harvard.edu/miguel-hernan/causal-inference-book/

The R code is based on the code by Joy Shi and Sean McGrath given [here](https://cdn1.sph.harvard.edu/wp-content/uploads/sites/1268/1268/20/Rcode_CIpart2.zip).

## Packages to install
To install the R packages required for this book please copy/fork the repository and run:

```r
# install.packages('devtools') # uncomment if devtools not
# installed
devtools::install_deps()
```

## Downloading the datasets
We assume that you have downloaded the data from the Causal Inference Book website and saved it to a `data` subdirectory. You can do this manually or with the following code (nb. we use the [`here`](https://here.r-lib.org/) package to reference the data subdirectory).


```r
library(here)
```


```r
dataurls <- list()
dataurls[[1]] <- "https://cdn1.sph.harvard.edu/wp-content/uploads/sites/1268/2012/10/nhefs_sas.zip"
dataurls[[2]] <- "https://cdn1.sph.harvard.edu/wp-content/uploads/sites/1268/2012/10/nhefs_stata.zip"
dataurls[[3]] <- "https://cdn1.sph.harvard.edu/wp-content/uploads/sites/1268/2017/01/nhefs_excel.zip"
dataurls[[4]] <- "https://cdn1.sph.harvard.edu/wp-content/uploads/sites/1268/1268/20/nhefs.csv"

temp <- tempfile()
for (i in 1:3) {
    download.file(dataurls[[i]], temp)
    unzip(temp, exdir = "data")
}

download.file(dataurls[[4]], here("data", "nhefs.csv"))
```

\mainmatter