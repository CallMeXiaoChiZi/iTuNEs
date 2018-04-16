# iTuNES User Manual

Chi Zhou  
Biological and Medical Big data Mining Lab  
Tongji University  
Shanghai, China. 

## Table of Contents
1. [General Description](#general-description)  
2. [Dependencies](#dependencies)  
    - [Required software](#required-software)  
    - [Python packages](#python-packages)  
3. [Installation](#installation)  
4. [Usage](#usage)  
5. [Input Files](#input-files)  
    - [VCF file](#vcf-file)  
    - [Expression file](#expression-file)  
    - [References](#references)  
6. [Output Files](#output-files)  
    - [Column explanation](#column-explanation)  
7. [Test Example](#test-example)  
    - [Data preparation](#data-preparation)  
        * [Recommended preprocessing of next generation sequencing (NGS)
data](#recommended-preprocessing-of-next-generation-sequencing-(ngs)-data)  
        * [Data cleanup](#data-cleanup)
        * [WXS data](#wxs-data)
        * [RNAseq](#rnaseq)
        * [HLA typing](#hla-typing)  

## General Description

Given matched tumor-normal whole exome sequencing and tumor RNA-seq sequencing data as input, iTuNes infers HLA sub-types, mutated peptides (neo-peptide), variant allele frequency, expression profile etc feature information. Based on these feature, a model- based refined ranking-score scheme could identify which of the neo-peptides have strong immunogecity.

## Dependencies  


#### Hardware:
iTuNEs currently test on x86_64 on ubuntu 16.04.

#### Required software:
* [Python 2.7](https://www.python.org/downloads/release/python-2712/)
* [R 3.2.3](https://cran.r-project.org/src/base/R-3/R-3.2.3.tar.gz)
* [NetMHCpan 4.0](http://www.cbs.dtu.dk/cgi-bin/nph-sw_request?netMHCpan)
* [Variant Effect Predictor (VEP)](https://github.com/Ensembl/ensembl-vep)
* [bwa](https://github.com/lh3/bwa)
* [samtools](https://github.com/samtools)
* [strelka](https://github.com/Illumina/strelka)
* [opitype](https://github.com/FRED-2/OptiType)
* [pyclone](https://bitbucket.org/aroth85/pyclone/wiki/Tutorial)
* [GATK 3.7](https://software.broadinstitute.org/gatk/best-practices/)
* [Picard tools](https://broadinstitute.github.io/picard/)
* [Java 8](https://java.com/en/download/help/linux_x64rpm_install.xml)
* [Varscan2](http://varscan.sourceforge.net/)
* [kallisto](http://pachterlab.github.io/kallisto/)
* [trimmomatic](http://www.usadellab.org/cms/?page=trimmomatic)
* [vcftools](http://vcftools.sourceforge.net/)
* [bllast](ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST/)


#### Python modules:
* [multiprocessing]
* [pyper]
* [sklearn]

## Installation 

1. Install all software listed above. 
2. Install multiprocessing, pyper and sklearn with the following command:

        pip install multiprocessing
        pip install pyper
        pip install sklearn


3. Download or clone the iTuNEs repository to your local system

        git clone https://github.com/XIAOCHIZI/iTuNES-dev.git

4.Reference data includes genome fasta, cDNA, peptide, cosmic reference(GRCh38 build)
could be downloaded through 
    `bash data_download,sh`

