## olink files:

Each olink experiment creates two files, the CT file created from the Biomark HD machine, and the processed NPX file created by the olink Manager software. One or more of these pairs of files can be uploaded at the same time.

Additionally for studies utilizing multiple batches, a harmonized and combined file can be created by the olink Manager software. This is usually refered to as the combined NPX file.

Example directory for olink data transfer:
```
.
├── olink_assay_1_CT.xlsx
├── olink_assay_1_NPX.xlsx
├── olink_assay_2_CT.xlsx
├── olink_assay_2_NPX.xlsx
├── olink_assay_combined.xlsx
└── olink_metadata_090219.xlsx
```

## olink metadata

The following section details the specific metadata collected for the olink assay.

### metadata model

### example metadata
Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/olink_template.xlsx) to see an example of a metadata file.

## Uploading Files

**Start the CLI and use your JWT to log in**
~~~~
cidc login [token]
~~~~

**Run upload command:**
~~~~
cidc assays upload --assay olink --xlsx olink_metadata_090219.xlsx
~~~~

The process will then use the metadata file to upload the required files
