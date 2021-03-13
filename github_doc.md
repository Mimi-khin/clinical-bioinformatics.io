Untitled
================

## GitHub Documents

This is an R Markdown format used for publishing markdown documents to
GitHub. When you click the **Knit** button all R code chunks are run and
a markdown file (.md) suitable for publishing to GitHub is generated.

## Including Code

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.3     v purrr   0.3.4
    ## v tibble  3.1.0     v dplyr   1.0.5
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   1.4.0     v forcats 0.5.1

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
#load the data
asthma_data <- read_excel("PheGenI_Association.xls", sheet=1)
```

``` r
# check the structure of data
str(asthma_data)
```

    ## tibble [712 x 17] (S3: tbl_df/tbl/data.frame)
    ##  $ #          : num [1:712] 1 2 3 4 5 6 7 8 9 10 ...
    ##  $ Trait      : chr [1:712] "Asthma" "Asthma" "Asthma" "Asthma" ...
    ##  $ SNP rs     : num [1:712] 1.17e+07 3.10e+06 1.45e+08 1.84e+06 2.02e+08 ...
    ##  $ Context    : chr [1:712] "intron" "nearGene-5" "intergenic" "intergenic" ...
    ##  $ Gene       : chr [1:712] "ZPBP2" "HLA-DQA1" "GTF3AP1" "SLC25A46" ...
    ##  $ Gene ID    : num [1:712] 1.25e+05 3.12e+03 1.00e+08 9.11e+04 8.81e+03 ...
    ##  $ Gene 2     : chr [1:712] "ZPBP2" "HLA-DQA1" "IL33" "TSLP" ...
    ##  $ Gene ID 2  : num [1:712] 124626 3117 90865 85480 9173 ...
    ##  $ Chromosome : num [1:712] 17 6 9 5 2 6 17 15 17 17 ...
    ##  $ Location   : num [1:712] 3.99e+07 3.26e+07 6.21e+06 1.11e+08 1.02e+08 ...
    ##  $ P-Value    : num [1:712] 1e-63 1e-40 1e-31 3e-31 5e-31 ...
    ##  $ Source     : chr [1:712] "NHGRI" "NHGRI" "NHGRI" "NHGRI" ...
    ##  $ PubMed     : num [1:712] 27182965 27182965 27182965 27182965 27182965 ...
    ##  $ Analysis ID: num [1:712] NA NA NA NA NA NA NA NA NA NA ...
    ##  $ Study ID   : num [1:712] NA NA NA NA NA NA NA NA NA NA ...
    ##  $ Study Name : chr [1:712] NA NA NA NA ...
    ##  $ Population : chr [1:712] "European" "European" "European" "European" ...

``` r
# Remove Duplicates and print the output to CSV file
print(remove_duplicate_snp)
```

    ## # A tibble: 433 x 2
    ##    Population  `SNP rs`
    ##    <chr>          <dbl>
    ##  1 European    11655198
    ##  2 European     3104367
    ##  3 European   144829310
    ##  4 European     1837253
    ##  5 European   202011557
    ##  6 European     2305480
    ##  7 European    56375023
    ##  8 European     3894194
    ##  9 European     2290400
    ## 10 European     2428494
    ## # ... with 423 more rows

``` r
write.csv(remove_duplicate_snp, file="snp and european pheno.csv", row.names=T)
```
