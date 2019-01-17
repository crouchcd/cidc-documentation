# Documentation for Whole Exome Sequencing Pipeline

# Table of Contents
- [Introduction](#introduction)
- [Wokflow](#workflow)
- [Pipeline Inputs](#input)
- [Pipeline Outputs](#output)

## Introduction <a name="introduction"></a>

CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from tumor sample. The pipeline includes 
tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.  The outputs of the pipeline includes
VCF files and MAF files.

## Workflow <a name="workflow"></a>

- Quality Control: FASTQC
- Alignment: bwa-mem
- Variant Calling: Mutect
- Variant Annotation: VEP

# Pipeline Input <a name="input"></a>
- Fastq files
- Metadata file

# Pipeline Output <a name="output"></a>
- VCF file
- MAF file
