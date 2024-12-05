# lab12
Gretel Warmuth (PID: A17595945)

> Q13: Read this file into R and determine the sample size for each
> genotype and their corresponding median expression levels for each of
> these genotypes.

``` r
res <- read.table("https://bioboot.github.io/bimm143_F24/class-material/rs8067378_ENSG00000172057.6.txt")
```

``` r
nrow(res)
```

    [1] 462

``` r
table(res$geno)
```


    A/A A/G G/G 
    108 233 121 

> Q14: Generate a boxplot with a box per genotype, what could you infer
> from the relative expression value between A/A and G/G displayed in
> this plot? Does the SNP effect the expression of ORMDL3?

``` r
library(ggplot2)
ggplot(res) + aes(geno, exp, fill = geno) +
  geom_boxplot(notch = T)
```

![](lab12_files/figure-commonmark/unnamed-chunk-4-1.png)
