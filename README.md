# Orchid DNA Analysis Verfication

## Description
To independently verify DNA analysis as published in The Plant Journal (2021) 107, 511-524, titled: "Repeat proliferation and partial endoreplication jointly shape the patterns of genomee size evolution in orchids"

## Steps
1. Download and install appropriate software
2. Download data
3. Execute scripts (TBD)


### 1. Software
#### Creating A Basic Development Environment
1. Anaconda (Anaconda3-2024.02-1 MacOSX-x86_64) : https://www.anaconda.com/download
2. Python (pycharm-community-2023.2.5) -- https://www.jetbrains.com/edu-products/download/download-thanks-pce.html
3. R (4.3.3 -- Angel Food Cake (for Mac Intel) package: R-4.3.3-x86_64.pkg) -- A) https://www.r-project.org/   B) Select "download R" 
   
#### Software Needed For This Project
1. SRA Toolkit (v3.1.0 - MacOS x86-64bit)  : https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit
2. HybPiper (v2.1.6)   : https://github.com/mossmatters/HybPiper/releases
      Depends on python
3. U.PhyloMaker (v0.1.0) : https://github.com/jinyizju/U.PhyloMaker/blob/master/U.PhyloMaker_0.1.0.tar.gz
      Depends on R.

### 2. Data
1. Sequencing data associated with the BioSample accession number SAMN13973793
   SRR11024140  : https://trace.ncbi.nlm.nih.gov/Traces/?view=run_browser&acc=SRR11028140&display=download
2. Data extraction using SRA Toolkit: fastq-dump --outdir /path/to/output/directory --split-files --gzip --origfmt SRR11028140
3. Target file: final_set_of_exons.fasta.  Downloaded from ![image](https://github.com/plitof1/Selby/assets/165665792/4ca9a0ba-48f8-4911-b7c5-f1680e51008b)

   
### 3. Execute Scrips
TBD

