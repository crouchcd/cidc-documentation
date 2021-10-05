# ATACseq

Assay for Transposase-Accessible Chromatin using sequencing (ATACseq) is used to assess genome-wide chromatin accessibility. Using a hyperactive transposase, the genome is fragmented and tagged with sequencing adaptors which are then amplified and sequenced. The more open the chromatin around a base, the more accessible it is to the transpose and so the more sequencing reads will align to that point.

## ATACseq Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the ATACseq metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## ATACseq Files

Each Whole Exome Sequencing experiment creates fastq.gz/bam files and a config file. **NOTE:** CIDC will process these into derivative results in a separate process coordinated by the CIDC Bioinformatics Team.

Example directory for ATAC-seq data transfer with fastq.gz files:

```bash
.
├── fwd.1.fastq.gz
├── rev.1.fastq.gz
├── fwd.2.fastq.gz
├── rev.2.fastq.gz
├── atacseq_fastq_metadata_20210624.xlsx
```

## ATACseq Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.atacseq_fastq_template.html) to see the specific metadata collected for the ATACseq assay (FASTQ format).

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/atacseq_fastq_template.xlsx) to see an example of a metadata xlsx file (FASTQ format).

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**

```bash
cidc login [token]
```

**The default environment is set to `production`. To switch to `staging` for testing purposes, run:**

```bash
cidc config set-env staging
```

**Run Assay-upload command, specifying the format as fastq:**

```bash
cidc assays upload --assay atacseq_fastq --xlsx atacseq_fastq_metadata_20210624.xlsx
```

The process will then use the metadata file to upload the required files. The files can be viewed on the portal [here](https://stagingportal.cimac-network.org/browse-files) once the upload is complete.
