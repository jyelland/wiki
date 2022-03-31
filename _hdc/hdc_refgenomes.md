---
title: Reference Genomes
hdc: True
---

When analyzing data generated by high-throughput genome sequencing
instruments, one common task is the comparison of those small genome fragments
against a reference genome of a known organism. Because multiple
groups may study the same organism, a collection of commonly used
reference files have been made available for use in high-performance
computing on the on-campus SLURM cluster. 
 
## iGenomes

The [iGenomes collection of reference genomes](https://support.illumina.com/sequencing/sequencing_software/igenome.html)
was developed by Illumina to provide a canonical source of reference genome information.
While that project is no longer actively updated, the available reference files have
been copied to a folder which is accessible at `/shared/biodata/reference/iGenomes/`.
The structure of those files is described below, and moving forward additional
reference genome indices may be generated which follow the same format and structure. 

## File Structure

All files described below can be found within the directory `/shared/biodata/reference/iGenomes/`: 

- The top-level folder in the iGenomes directory is named for the source organism: e.g. `/shared/biodata/reference/iGenomes/Homo_sapiens`; 

- The second-level folder is named for the source of the annotation used for the reference genome: e.g. `/shared/biodata/reference/iGenomes/Homo_sapiens/UCSC`; 

- The third-level folder is named for the version of the genome: e.g. `/shared/biodata/reference/iGenomes/Homo_sapiens/UCSC/hg19`; 

- The fourth-level folders are `Annotation` and `Sequence`; 

    - The `Annotation` folder contains a folder `Genes` and may also contain `SmallRNA` and `Variation`. The exact files provided for each genome may vary, but `Genes` may contain `genes.bed` and `genes.gtf` to describe exon structure of genes, while `SmallRNA` may contain `hairpin.fa` and `mature.fa` to describe miRNAs; 

    - The `Sequence` folder contains a folder `WholeGenomeFasta` and `Chromosomes` which contain the FASTA sequence of the reference genome, either in full or broken out by chromosome, respectively; 

    - The `Sequence` folder also contains a set of references which have been pre-compiled for various alignment / analysis algorithms, which may include: 

        - `BismarkIndex`
        - `BlastDB`
        - `Bowtie2Index`
        - `BowtieIndex`
        - `BWAIndex`
        - `MDSBowtieIndex`
        - `STARIndex`: For STAR < 2.7.6a 
        - `STAR2Index`: For STAR ≥ 2.7.6a 

## Example

Below is an example of the folders available for the UCSC human genome GRCh37/hg19 reference: 

``` 
├── Homo_sapiens                        # Organism 
│   └── UCSC                            # Source 
│       ├── hg19                        # Version 
│       │   ├── Annotation
│       │   │   ├── Genes               # Gene annotations 
│       │   │   ├── README.txt 
│       │   │   ├── SmallRNA            # Small RNA annotations 
│       │   │   └── Variation           # Variant annotations 
│       │   └── Sequence 
│       │       ├── AbundantSequences	 
│       │       ├── BismarkIndex        # Index for Bismark 
│       │       ├── BlastDB             # Index for BLAST 
│       │       ├── Bowtie2Index        # Index for Bowtie2 
│       │       ├── BowtieIndex         # Index for Bowtie 
│       │       ├── BWAIndex            # Index for BWA 
│       │       ├── Chromosomes         # Genome sequence by chromosome 
│       │       ├── MDSBowtieIndex      # Index for MDS Bowtie 
│       │       ├── STARIndex           # Index for STAR 
│       │       ├── STAR2Index          # Index for STAR2 
│       │       └── WholeGenomeFasta    # Genome sequence 
``` 

## Ongoing Support

To maintain the utility of this data resource, the Bioinformatics Core and the Data Core
will incrementally add reference genomes for additional organisms and alignment algorithms.
If your research group is interested in using an organism or alignment algorithm which
is not currently available, please [get in touch](mailto:hutchdatacore@fredhutch.org).