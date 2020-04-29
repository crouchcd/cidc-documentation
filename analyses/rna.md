# RNA Expression

RNA sequencing techniques are employed for transcriptome analysis in various sample types.

## RNA Seq Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the RNA Expression metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.

## RNA Seq Analysis Files

Example directory for RNA Expression analysis data transfer:
```
.
├── rna-analysis
│   ├── analysis1.bam
│   ├── analysis1.bam.bai
│   └── ..
├── rna_analysis_30012020.xlsx
```

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run Analysis-upload command**
```bash
cidc analyses upload --analysis rna_analysis --xlsx rna_analysis_010720.xlsx
```
The process will then use the template to upload the analysis files. The files can be viewed on the portal [here](https://stagingportal.cimac-network.org/browse-files) once the upload is complete.
