# CyTOF
Mass cytometry, or CyTOF, is an evolution of flow cytometry in which antibodies are labeled with heavy metal ions. Protein abundance in single cells are quantified by time-of-flight mass spectrometry. The properties of the metal-labeling technology and specificity of mass cytometry allow for the measurement of many markers at once without significant spillover between channels.

## CyTOF Workflow Overview
1. The CIMAC technician who is performing the experiment downloads a copy of the CyTOF metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis. Concatenation, normalization and de-barcoding should be done by the CIMAC technician according to the agreed upon protocol. One prepared FCS file should be created per sample.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet which point to the resultant FCS files.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the raw and proccessed FCS files to CIDC using the command line tool.


## CyTOF Files

Each CyTOF experiment creates one or more raw FCS files and a single processed FCS per sample. One or more of these sets of files can be uploaded at a time.

Example directory for CyTOF data transfer:
```
.
├── cytof_raw1.fcs
├── cytof_raw2.fcs
├── cytof_processed1.fcs
├── cytof_processed2.fcs
├── cytof_vericell1.fcs
├── cytof_vericell2.fcs
├── cytof_batch_control.fcs
├── cytof_batch_control_vericell.fcs
├── cytof_debarcoding_key.csv.fcs
└── cytof_metadata_090219.xlsx
```

## CyTOF Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/templates.metadata.cytof_template.html) to see the specific metadata collected for the CyTOF assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/cytof_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay cytof --xlsx cytof_metadata_090219.xlsx
```

The process will then use the metadata file to upload the required files.
