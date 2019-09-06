## Introduction to WES

CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from tumor sample. The pipeline includes 
tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.

## WES Workflow Overview

1. The CIMAC technician who is performing the experiment will download a copy of the WES metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician will begin populating the metadata spreadsheet. 
(**NOTE** If the biospecimens have not be relabled to use CIMAC ids, then the technician should *digitally* re-label the sample by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.)
3. The CIMAC technician will perform the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support will fill in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support will transfer the metadata and files to CIDC using the command line tool.

## WES files

Each Whole Exome Sequencing experiment requires fastq files and a config file. **NOTE** CIDC will process the fastq files into derivative results in a seperate process coordinated by the CIDC bioinformatics team. 

Example directory for WES data transfer:
```
.
├── fwd.1.1.1.fastq.gz
├── fwd.2.2.2.fastq.gz
├── rev.1.1.1.fastq.gz
├── rev.2.2.2.fastq.gz
├── rgm.1.1.1.txt
├── rgm.2.2.2.txt
├── wes_metadata_082919.xlsx
```

## WES metadata


Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.wes_template.html) to see the specific metadata collected for the WES assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/wes_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your JWT to log in**
~~~~
cidc login [token]
~~~~

**Run upload command:**
~~~~
cidc assays upload --assay wes --xlsx wes_metadata_082919.xlsx
~~~~

The process will then use the metadata file to upload the required files.
