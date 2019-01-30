## Introduction

CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from tumor sample. The pipeline includes 
tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.  The outputs of the pipeline includes
VCF files and MAF files.

## Workflow 

- Quality Control: FASTQC
- Alignment: bwa-mem
- Variant Calling: Mutect
- Variant Annotation: VEP

## Inputs 
- Fastq files
- Config file

## Outputs 
- VCF file
- MAF file
