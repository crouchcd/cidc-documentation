# Microbiome

16S rRNA amplicon sequencing provides the relative or absolute abundance of microbes in a biological sample. Microbial DNA and the V4 hypervariable region of the 16S rRNA gene is amplified by PCR, sequencing is run, and computational analysis is performed to determine relative abundances of taxa, alpha-, and beta diversity, and association taxa with phenotypes. Characterization of the microbiome may help to stratify immunotherapy responders from non-responders, contribute to the development of microbiome-based combination therapy to improve response rate, and/or reduce adverse events, such as colitis.

## Microbiome Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the Microbiome metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the data files to a CIDC upload bucket, following the concierge model.
6. The CIDC engineer support transfers the metadata and data files to CIDC using the command line tool.


## Microbiome Files

Each Microbiome experiment creates fastq.gz files. The CIMAC also provides and OTU table and experiment summary.

Example directory for Microbiome data transfer:
```
.
├── fwd.1.fastq.gz
├── rev.1.fastq.gz
├── fwd.2.fastq.gz
├── rev.2.fastq.gz
├── microbiome_otu.tsv
├── microbiome_summary.pdf
└── microbiome_metadata_102522.xlsx
```

## Microbiome Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.microbiome.microbiome_template.html) to see the specific metadata collected for the Microbiome assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/microbiome_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay microbiome --xlsx microbiome_metadata_102522.xlsx
```

The process will then use the metadata file to upload the required files.
