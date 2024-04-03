# Orchid DNA Analysis Verfication

## Description
To independently verify DNA analysis as published in The Plant Journal (2021) 107, 511-524, titled: "Repeat proliferation and partial endoreplication jointly shape the patterns of genomee size evolution in orchids"

## Steps
1. Download and install appropriate software
2. Download data
3. Execute scripts (TBD)


### 1. Software
1. SRA Toolkit (v3.1.0 - MacOS x86-64bit)  : https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit
2. HybPiper (v2.1.6)   : https://github.com/mossmatters/HybPiper/releases
3. U.PhyloMaker (v0.1.0) : https://github.com/jinyizju/U.PhyloMaker/blob/master/U.PhyloMaker_0.1.0.tar.gz

### 2. Data
1. Sequencing data associated with the BioSample accession number SAMN13973793
   SRR11024140  : https://trace.ncbi.nlm.nih.gov/Traces/?view=run_browser&acc=SRR11028140&display=download
2. Data extraction using SRA Toolkit: fastq-dump --outdir /path/to/output/directory --split-files --gzip --origfmt SRR11028140
   
### 3. Execute Scrips
TBD

