# TCR

T-cell receptor sequencing (TCRseq) is an extension of RNAseq that uses a mix of primers specific for the TCR to study the diversity of these receptors. As T cells are highly important in cell-based immunity, describing their varieties and distribution provides a window into the function of the adaptive immune system.

## TCR Workflow Overview
1. The CIMAC technician who is performing the experiment downloads a copy of the TCRseq metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and data files to CIDC using the command line tool.


## TCR Analysis Files

Example directory for TCRseq analysis data transfer:
```
.
├── CTTTPP111.00/1A_10_0_TRA_clones_umi_count.csv
├── CTTTPP111.00/1A_10_0_TRB_clones_umi_count.csv
├── CTTTPP121.00/2A_10_0_TRA_clones_umi_count.csv
├── CTTTPP121.00/2A_10_0_TRB_clones_umi_count.csv
├── summary_info.csv
└── tcr_analysis_20201023.xlsx
```

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc analyses upload --analysis tcr_analysis --xlsx tcr_analysis_20201023.xlsx
```

The process will then use the analysis template to upload the required analysis files.
