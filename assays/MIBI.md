# Multiplexed Ion Beam Imaging (MIBI)

MIBI uses secondary ion mass spectrometry to image targets using antibodies tagged with heavy metal reporters and yields a mass spectrometry readout. It can analyze up to 100 targets simultaneously, can provide new insights by integrating tissue microarchitecture with highly multiplexed protein expression patterns, and can offer valuable information for basic research, as well as clinical diagnostics.

## MIBI Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the MIBI metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the data files to a CIDC upload bucket, following the concierge model.
6. The CIDC engineer transfers the metadata and the data files to CIDC using the command line tool.


## MIBI Files

Each MIBI experiment creates a multichannel image, cluster-labelled image, channel name table, and single cell data table for each sample.

Example directory for MIBI data transfer:
```
.
├── mibi_metadata.tsv
├── multichannel_image.ome.tiff
├── cluster_labels_image.tif
├── channelnames_report.csv
├── single_cell_tables.csv
└── mibi_metadata_102522.xlsx
```

## MIBI Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.mibi.mibi_template.html) to see the specific metadata collected for the MIBI assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/mibi_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay mibi --xlsx mibi_metadata_102522.xlsx
```

The process will then use the metadata file to upload the required files.
