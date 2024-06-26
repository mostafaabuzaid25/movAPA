# movAPA v0.2.0 (released on 2023/10/10)
**Mo**deling and **v**isualization of dynamics of **a**lternative **p**oly**a**denylation across biological samples

## About
Alternative polyadenylation (APA) has been widely recognized as a widespread mechanism modulated dynamically. Studies based on 3′ end sequencing and/or RNA-seq have profiled poly(A) sites in various species with diverse pipelines, yet no unified and easy-to-use toolkit is available for comprehensive APA analyses. We developed an R package called __movAPA__ for **mo**deling and **v**isualization of dynamics of **a**lternative **p**oly**a**denylation across biological samples. movAPA incorporates rich functions for preprocessing, annotation, and statistical analyses of poly(A) sites, identification of poly(A) signals, profiling of APA dynamics, and visualization. Particularly, seven metrics are provided for measuring the tissue-specificity or usages of APA sites across samples. Three methods are used for identifying 3′ UTR shortening/lengthening events between conditions. APA site switching involving non-3′ UTR polyadenylation can also be explored. Using poly(A) site data from rice and mouse sperm cells, we demonstrated the high scalability and flexibility of movAPA in profiling APA dynamics across tissues and single cells.

* The movAPA package consists of seven main modules.

<img src="img/schema.png" width="100%" />

A. Poly(A) sites of biological samples obtained from 3’ seq or RNA-seq are stored in the PACdataset object and further preprocessed for the removal of internal priming artifacts and normalization.

B. The genome annotation file in GFF3/GTF format is processed, then poly(A) sites are annotated with rich information such as gene id, gene type, and genomic regions. 

C. Statistical analyses can be conducted to profile the global landscape of poly(A) site distributions and count the overlap with other poly(A) site datasets. 

D. Sequences surrounding poly(A) sites can be extracted and poly(A) signals of specific regions can be identified. 

E. Three metrics can be adopted for the quantification of the usage of each poly(A) site across samples and four metrics are used for the quantification of dynamic APA site usage of a gene. 

F. APA dynamics across biological samples can be profiled, including the detection of differentially expressed poly(A) sites and genes, 3′ UTR lengthening/shortening events, and canonical or non-canonical APA site switching events. 

G. Rich functions are provided for the visualization of poly(A) site distributions and dynamic APA site usages across selected biological samples or single cells. 


## Getting started
### Mandatory
* R (>=3.5.0). [R 3.6.3](https://www.r-project.org/) is recommended.

### Required R Packages
* Matrix, dplyr, reshape2, IRanges, GenomicRanges, RColorBrewer, data.table, ggplot2, Biostrings, BSgenome, ggbio, methods, magrittr, GenomicFeatures

### Installation
* Install the R package using the following commands on the R console:

```
install.packages("devtools")
require(devtools)
install_github("mostafaabuzaid25/movAPA")
library(movAPA)
browseVignettes('movAPA')

##or you can download ZIP, and then unzip
devtools::install_local("your_path_of_movAPA-master.zip", build_vignettes = TRUE)
```

## Application examples
### Read a poly(A) site file with movAPA
This documentation describes how to read an external file of poly(A) sites and analyze it with movAPA. We used the model species – Arabidopsis for demonstration.
Please refer to the vignette ([PDF](https://github.com/BMILAB/movAPA/blob/master/inst/doc/movAPA_data_input.pdf), [HTML]( https://bmilab.github.io/movAPA/vignettes/movAPA_data_input.html)) for full details. 

### Dynamics of APA across rice tissues
In this case study, we investigated the application of movAPA on a poly(A) site dataset of multiple tissues in _Oryza sativa japonica_ from 3’ end sequencing. 
Please refer to the vignette ([PDF](https://github.com/BMILAB/movAPA/blob/master/inst/doc/movAPA_on_rice_tissues.pdf), [HTML]( https://bmilab.github.io/movAPA/vignettes/movAPA_on_rice_tissues.html)) for full details. 
The data in the vignette can be downloaded from the __refer__ branch-"[demo_data](https://github.com/BMILAB/movAPA/tree/refer)".
```
## You can also browse the vignette using the following command on the R console
vignette("movAPA_on_rice_tissues", package = "movAPA")
```
### Dynamics of APA in mouse sperm cells
movAPA is highly scalable and flexible, which can be used for profiling APA dynamics in single cells. Here we investigated the application of movAPA on poly(A) sites from mouse sperm cells. Poly(A) sites from three stages of differentiation process were obtained from the previous study (Shulman and Elkon, 2019), including early stage (spermatocytes, SC), intermediate stage (round spermatids, RS), and late stage (elongating spermatids, ES).
Please refer to the vignette ([PDF](https://github.com/BMILAB/movAPA/blob/master/inst/doc/movAPA_on_mouse_sperm_cells.pdf), [HTML]( https://bmilab.github.io/movAPA/vignettes/movAPA_on_mouse_sperm_cells.html)) for full details.
```
## You can also browse the vignette using the following command on the R console
vignette("movAPA_on_mouse_sperm_cells", package = "movAPA")
```
### Analyze APA results from scAPAtrap with the movAPA package
This documentation describes how to read an external file of single-cell poly(A) sites generated by [scAPAtrap](https://github.com/BMILAB/scAPAtrap/) and analyze it with movAPA.
Please refer to the vignette ([PDF](https://github.com/BMILAB/movAPA/blob/master/inst/doc/movAPA_on_scAPAtrap_results.pdf), [HTML]( https://bmilab.github.io/movAPA/vignettes/movAPA_on_scAPAtrap_results.html)) for full details.
```
## You can also browse the vignette using the following command on the R console
vignette("movAPA_on_scAPAtrap_results", package = "movAPA")
```
## Citation
If you are using movAPA, please cite: [Wenbin Ye#, Tao Liu#, Hongjuan Fu, Congting Ye, Guoli Ji*, and Xiaohui Wu*: movAPA: Modeling and visualization of dynamics of alternative polyadenylation across biological samples, Bioinformatics, 2020.](https://academic.oup.com/bioinformatics/advance-article-abstract/doi/10.1093/bioinformatics/btaa997/6015116)
