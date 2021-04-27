# Pocket_16S
**Requirements 

Python 2.7 or higher 

Pandas for Python 

Seqkit 

BLAST Plus with 16S database 

Windows (Windows 7 or higher) 

Note: Ubuntu 18.04 or higher is possible (not tested). 

 

Description 

Pocket_for_16S is a simple tool used for offline bacteria identification of clinical isolates, using NCBI 16S ribosomal RNA database. The input file is 16S rRNA sequences in either fasta or fastq format. However, if fastq file is used, it will be converted to fasta file prior to the BLAST Plus analysis. The output files of BLAST Plus analysis will be hit table CSV. The top three (by default) abundant of identified bacteria will be reported. 

 

Installation 

Please install BLAST Plus and download the 16S ribosomal RNA database by following the official instructions (https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download). Please also make sure you have installed seqkit (https://github.com/shenwei356/seqkit/releases) and python (https://www.python.org) with pandas (https://pandas.pydata.org/). After that, download the python file package containing two python files, one for fastq files and one for fasta files. Change the path to your installed BLAST Plus and database in the python files. 

 

Basic usage 

Each time you run an analysis, make a folder named “pocket” and copy the fastq/fasta files to be analyzed into it. Then run the following command in the Pocket_for_16S folder: 

 

python 16S_fastq_input.py #for fastq files 

python 16S_fasta_input.py #for fasta files 

 

The default setting of BLAST Plus is as follows: 

    Percentage identity 90% 

    Query cover 90% 

    Top three ranked alignments will be shown. 

The pocket folder can be renamed for data backup after the analysis. 

 

Analyzing Nanopore sequencing data 

The fastq files generated from Nanopore sequencing should be first concatenated into one single fastq file per sample. Then, copy the concatenated fastq files to the “pocket” folder and execute the python script for fastq files. The resulting CSV files will be generated in the “pocket”. 

 

Analyzing Illumina sequencing data 

Before the classification using BLAST plus, the pair end reads generated from Illumina sequencing needed to be merged and filtered using tools such as Mothur (https://mothur.org/). The resulting fasta file of each sample is copied to the “pocket” folder and execute the python script for fasta files. CSV files will be generated in the “pocket”. 
