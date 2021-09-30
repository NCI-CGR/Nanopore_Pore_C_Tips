# Nanopore_Pore_C_Tips
## Description
This Documentation provides some tips for running [Nanopore Pore C pipeline](https://github.com/nanoporetech/Pore-C-Snakemake)
## Tips
* Required input files:

  a) a merged fastq file for each sample
  
  b) raw fast5 files stored in one directory for each sample
  
  c) a sequencing_summary text file for each sample
  
  d) reference genome fasta file. The "GRCh38.fasta.gz" file provided by the original pipeline is NOT a real fasta file. 
  
* To run on cluster

  a) the correct conda environment name is : conda activate pore-c-snakemake, NOT pore_c_snakemake as shown in the original repo.

  b) allow more than 4G memory for running snakemake, otherwise some conda environment installation may fail. 
  
  c) log files are stored at: results/logs/results/
  
* Output

  a) without phased vcf file: 
   
     align_table/
     
     basecall/
     
     benchmarks/
     
     contacts/
     
     logs/
     
     mapping/
     
     merged_contacts/
     
     refgenome/
     
     virtual_digest/
     
   b) a extra step is needed to merged all splited bam files
   
   c) the DNA contact information is stored in the file: merged_contacts/*.concatemers.parquet. Convert it to the CVS format if needed.  
     
  
