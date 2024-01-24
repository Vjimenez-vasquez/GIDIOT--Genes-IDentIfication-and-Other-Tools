## 1 : Download from FTP and prepare database ##
```r
wget 'ftp://ftp.ncbi.nlm.nih.gov/blast/db/FASTA/nr.gz'
gunzip -k nr.gz
mv nr nr.fasta
```
## 2 : Download SRA files ##
```r
1. Download "Ubuntu Linux 64 bit architecture" SRA-TOOLKIT from : 
https://github.com/ncbi/sra-tools/wiki/01.-Downloading-SRA-Toolkit
2. Uncompress with
tar -vxzf sratoolkit.3.0.10-ubuntu64.tar.gz
3. export to bin
export PATH=$PATH:$PWD/sratoolkit.3.0.10-ubuntu64/bin
4. generate a txt file with all SRA accessions
5.  Download SRA files
prefetch --option-file SRA_ACCESSIONS_LIST.txt ; 
fasterq-dump --split-files *.sra ;
fastqc -t 4 *.fastq ;
```
