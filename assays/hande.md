# H & E
Hematoxylin and Eosin cellular/tissue staining in histology.

## H & E Workflow Overview
1. The CIMAC technician who is performing the experiment downloads a copy of the H&E metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the sample by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet which point to the resultant files.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and files to CIDC using the command line tool.


## H&E Files

Example directory for H&E data transfer (all files should be in the same directory):
```
.
├── image_file_1.svs
├── image_file_2.svs
└── hande_metadata_11012021.xlsx
```

## H&E Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.hande_template.html) to see the specific metadata collected for the H&E assay.


## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay hande --xlsx hande_metadata_11012021.xlsx
```

The process will then use the metadata file to upload the required files.
