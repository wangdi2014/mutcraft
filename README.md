# Getting started
Mutcraft is a package of funtions to read somatic mutation information from VCF files and visualize spectra, rainplots, strand bias and mutational signatures.

## Installation
```{r eval=FALSE}
library(mutcraft)
```



## Reference genome
In order to extract mutation contexts and mutation strands you need to load a reference genome

```{r eval=FALSE}
library(BSgenome)
ref_genome = "BSgenome.Hsapiens.NCBI.GRCh37"
library(ref_genome, character.only = T)
```



## Load files
```{r eval=FALSE}
my.files <- c("myfile1.vcf","myfile2.vcf")
s.names <- c("sample1", "sample2")
mutnet <- mc.loadVcfs(my.files,s.names, ref.genome=ref_genome)
```

## Mutation Spectrum
```{r eval=FALSE}
mutspec <- lapply(mutnet,mc.mutSpectrum,"col.ref"="ref.allele","col.alt"="alt.allele")
mc.plotSpectrum(mutspec,"prop",print.num=F)
```
