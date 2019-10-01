# Repository of R code for the Causal Inference Book Examples

## Install dependencies
If you have downloaded/forked this repository you can install the dependencies that are on CRAN with (assuming your working directory is at the top level of the repo):
```r
# install.packages("devtools") # uncomment if devtools not installed
devtools::install_deps()
```

## Building the book

- Render all formats
```r
rmarkdown::render_site(encoding = 'UTF-8')
```

- Render the PDF book
``` r
rmarkdown::render_site(output_format = 'bookdown::pdf_book', encoding = 'UTF-8')
```

- Render the HTML book
``` r
rmarkdown::render_site(output_format = 'bookdown::gitbook_book', encoding = 'UTF-8')
```

- Preview a specific chapter
``` r
bookdown::preview_chapter("chapter-filename.Rmd")
```