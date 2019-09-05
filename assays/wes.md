## Introduction

CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from tumor sample. The pipeline includes 
tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.  The outputs of the pipeline includes
VCF files and MAF files.

## Workflow 

- Quality Control: FASTQC
- Alignment: bwa-mem
- Variant Calling: Mutect
- Variant Annotation: VEP

## Olink Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.wes_template.html) to see the specific metadata collected for the WES assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/wes_template.xlsx) to see an example of a metadata xlsx file.


## Inputs 
- Fastq files
- Config file

## Outputs 
- VCF file
- MAF file
