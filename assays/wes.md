# WES

Whole exome sequencing (WES) is an assay used to sequence the coding regions of the genome. The CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from WES of tumor samples. The pipeline includes tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.

## WES Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the WES metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## WES Files

Each Whole Exome Sequencing experiment creates fastq.gz/bam files and a config file. **NOTE:** CIDC will process these into derivative results in a separate process coordinated by the CIDC Bioinformatics Team. 

Example directory for WES data transfer with fastq.gz files:
```
.
├── fwd.1.fastq.gz
├── rev.1.fastq.gz
├── fwd.2.fastq.gz
├── rev.2.fastq.gz
├── wes_fastq_metadata_082919.xlsx
```

Example directory for WES data transfer with bam files:
```
.
├── 1.bam
├── 2.bam
├── wes_fastq_metadata_082919.xlsx
```

## WES Metadata


Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.wes_fastq_template.html) to see the specific metadata collected for the WES assay (FASTQ format).

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.wes_bam_template.html) to see the specific metadata collected for the WES assay (BAM format).


Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/wes_fastq_template.xlsx) to see an example of a metadata xlsx file (FASTQ format).

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/wes_bam_template.xlsx) to see an example of a metadata xlsx file (BAM format).

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**The default environment is set to `production`. To switch to `staging` for testing purposes, run:**
```bash
cidc config set-env staging
```

**Run Assay-upload command, specifying the format as either fastq or bam:**
```bash
cidc assays upload --assay wes_<format> --xlsx wes_metadata_082919.xlsx
```

**Run Analysis-upload command**
```bash
cidc analyses upload --analysis wes_analysis --xlsx wes_analysis_010720.xlsx
```
The process will then use the metadata file to upload the required files. The files can be viewed on the portal [here](https://stagingportal.cimac-network.org/browse-files) once the upload is complete.