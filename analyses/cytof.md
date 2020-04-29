# CyTOF
Mass cytometry, or CyTOF, is an evolution of flow cytometry in which antibodies are labeled with heavy metal ions. Protein abundance in single cells are quantified by time-of-flight mass spectrometry. The properties of the metal-labeling technology and specificity of mass cytometry allow for the measurement of many markers at once without significant spillover between channels.

## CyTOF Workflow Overview
1. The CIMAC technician who is performing the experiment downloads a copy of the CyTOF metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis. Concatenation, normalization and de-barcoding should be done by the CIMAC technician according to the agreed upon protocol. One prepared FCS file should be created per sample.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet which point to the resultant FCS files.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the raw and proccessed FCS files to CIDC using the command line tool.


## CyTOF Analysis Files

Example directory for CyTOF analysis data transfer:
```
.
├── CTTTPP111.00/fcs.fcs
├── CTTTPP111.00/assignment.csv
├── CTTTPP111.00/comp.csv
├── CTTTPP111.00/profiling.csv
├── CTTTPP111.00/cca.csv
├── CTTTPP111.00/ccc.csv
├── CTTTPP111.00/ccp.csv
└── cytof_analysis_090219.xlsx
```

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc analyses upload --analysis cytof --xlsx cytof_analysis_090219.xlsx
```

The process will then use the analysis template to upload the required analysis files.
