# WES

Whole exome sequencing (WES) is an assay used to sequence the coding regions of the genome. The CIDC Whole Exome Pipeline is a computational workflow for identifying somatic variants from WES of tumor samples. The pipeline includes tools for quality control (QC) and characterization of paired (tumor/normal) whole exome sequencing data.

## WES Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the WES metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## WES Analysis Files

Example directory for WES analysis data transfer:
```
.
├── wes-analysis
│   ├── analysis1.bam
│   ├── analysis1.bam.bai
│   └── ..
├── wes_analysis_30012020.xlsx
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

**Run Analysis-upload command**
```bash
cidc analyses upload --analysis wes_analysis --xlsx wes_analysis_010720.xlsx
```
The process will then use the template to upload the analysis files. The files can be viewed on the portal [here](https://stagingportal.cimac-network.org/browse-files) once the upload is complete.