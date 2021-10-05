# ATACseq

TODO

## ATACseq Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the ATACseq metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## ATACseq Analysis Files

Each Whole Exome Sequencing experiment creates fastq.gz/bam files and a config file. **NOTE:** CIDC will process these into derivative results in a separate process coordinated by the CIDC Bioinformatics Team.

Example directory for ATAC-seq data transfer with fastq.gz files:

```bash
.
├── analysis/peaks/*
├── analysis/report/*
├── analysis/align*
├── filled_atacseq_analysis.xlsx
```

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**

```bash
cidc login [token]
```

**The default environment is set to `production`. To switch to `staging` for testing purposes, run:**

```bash
cidc config set-env staging
```

**Run Analysis-upload command, specifying the format as fastq:**

```bash
cidc analyses upload --analysis atacseq_fastq_analysis --xlsx filled_atacseq_analysis.xlsx
```

The process will then use the template to upload the analysis files. The files can be viewed on the portal [here](https://stagingportal.cimac-network.org/browse-files) once the upload is complete.
