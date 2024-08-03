# Dragmap 

Dragmap is the Dragen mapper/aligner Open Source Software.

## Installation

### Build from source

#### Install


The basic procedure is

    export HAS_GTEST=0
    export STATIC=1
    make -j 4

Binary will be generated in ./build/release/

Then optionally, to install to /usr/bin/

    make install


## Basic command line usage 

### Command line options 

    dragen-os --help


### Build hash table of a reference fasta file 

    dragen-os --build-hash-table true --ht-reference reference.fasta  --output-directory /home/data/reference/

### Build hash table using an alt-masked bed file

    dragen-os --build-hash-table true --ht-reference hg38.fa  --output-directory /home/data/reference/ --output-file-prefix=dragmap.hg38_alt_masked --ht-mask-bed=fasta_mask/hg38_alt_mask.bed

### Align paired-end reads :

Output result to standard output 

    dragen-os -r /home/data/reference/ -1 reads_1.fastq.gz -2 reads_2.fastq.gz >  result.sam

Or directly to a file :

    dragen-os -r /home/data/reference/ -1 reads_1.fastq.gz -2 reads_2.fastq.gz --output-directory /home/data/  --output-file-prefix result

### Align single-end reads :

    dragen-os -r /home/data/reference/ -1 reads_1.fastq.gz  >  result.sam


## Pull requests

We are not accepting pull requests into this repository at this time, in particular because of conflicts concerns with our internal repository. For any bug report / recommendation / feature request, please open an issue.
