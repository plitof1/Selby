# Orchid DNA Analysis Verfication

## Description
To independently verify DNA analysis as published in The Plant Journal (2021) 107, 511-524, titled: "Repeat proliferation and partial endoreplication jointly shape the patterns of genomee size evolution in orchids"

## Steps
1. Download and install appropriate software
2. Download data
3. About FASTA files
4. Execute scripts (TBD)


### 1. Software
#### Creating A Basic Development Environment
1. Anaconda (Anaconda3-2024.02-1 MacOSX-x86_64) : https://www.anaconda.com/download
2. Python (pycharm-community-2023.2.5) -- https://www.jetbrains.com/edu-products/download/download-thanks-pce.html
3. R (4.3.3 -- Angel Food Cake (for Mac Intel) package: R-4.3.3-x86_64.pkg) -- A) https://www.r-project.org/   B) Select "download R" 
   
#### Software Needed For This Project
1. SRA Toolkit (v3.1.0 - MacOS x86-64bit)  : https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit
2. HybPiper (v2.1.6)   : https://github.com/mossmatters/HybPiper/releases
3. U.PhyloMaker (v0.1.0) : https://github.com/jinyizju/U.PhyloMaker/blob/master/U.PhyloMaker_0.1.0.tar.gz
4. FASTAFileFix.pl : 

### 2. Data
1. Sequencing data associated with the BioSample accession number SAMN13973793
   SRR11024140  : https://trace.ncbi.nlm.nih.gov/Traces/?view=run_browser&acc=SRR11028140&display=download
2. Data extraction using SRA Toolkit: fastq-dump --outdir /path/to/output/directory --split-files --gzip --origfmt SRR11028140
3. Target file: final_set_of_exons.fasta.  Provided in email.
   - The headers in this file were seen as invalid by HybPiper
   - To resolve the issues the first character of each header was changed from a ">" to a "@"

### 3. About FASTA Files
FASTA files must be formatted based on a specific set of standards.  You can find "most" of them using the following links: 
   https://github.com/mossmatters/HybPiper/wiki#12-target-file
   https://github.com/mossmatters/HybPiper/wiki/Troubleshooting,-common-issues,-and-recommendations
   https://en.wikipedia.org/wiki/FASTA_format
   
What I did not find but learns is that everything to the right of the last "_" (underscore) is considered the name of the gene. If you want to include information in the DNA header line about the gene use a "." instead.  Let's assume you want to do research based on specific "contigs" of a gene rather than the entire gene. (NOTE: it is recommended that you "don't" do this rather do the research using the entire DNA string.)  
For example: Assume your gene is ABat123, with 3 contigs and you want to include the length of each contig in your header.  
   - The headers you think you want to use are; >Gene_ABat123_contig1_232, >Gene_ABat123_config2_168, >Gene_ABat123_congig3_421.
   - The ISSUE:
      - hybpiper will take everything after the right mosts "_" and treat that as the gene name
      - Therefore the genes will be 232, 168 and 421.
      - If you have other genes in your FASTA file with similar lengths (232, 168, 421) hybpiper will get confused and make a big mess
   - Therefore a better header naming format would be; >Gene_ABat123.1.232, >Gene_ABat123.2.168, >Gene_ABat123.3.421.
   - Then hybpiper will generate gene unique names of; ABat123.1.232, ABat123.2.168, ABat123.3.421    

FASTA files should generally have the following format: 
   1. The header can be no more than 25 characters
   2. The DNA string should be broken into lines of no more than 80 characters
   3. As of 04/23/2024 #1 is up to you, the FASTAFileFix.pl will in sure #2 is satisfied.    

### 4. Execute Scrips
1. hybpiper check_targetfile --t_dna file_set_of_exons.fasta 
2. hybpiper assemble -t_dna final_set_of_exons.fasta -r SRR11028140.fastq --bwa --prefix Dracula
3. 

