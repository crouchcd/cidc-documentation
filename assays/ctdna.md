# Circulating Tumor DNA (ctDNA)

ctDNA may reflect the entire tumor genome diversity; it has gained traction for its potential clinical utility as “liquid biopsies” measured in plasma or serum to monitor tumor progression, predict treatment response or relapse, or determine target driver mutations. Both WES and targeted approaches using histology-specific gene panels are standardized and are available at CIMACs for ctDNA detection.

## ctDNA Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the ctDNA metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the data files to a CIDC upload bucket, following the concierge model.
6. The CIDC engineer support transfers the metadata and data files to CIDC using the command line tool.


## ctDNA Files

Each ctDNA experiment creates a bam with an associated bam index for every sample. The CIMAC also provides mutiple plots and graphics from the experiment.

Example directory for ctDNA data transfer:
```
.
├── ctdna_summary_plot.pdf
├── ctdna_demultiplexed.bam
├── ctdna_bam_index.bai
├── ctdna_genome_wide_plots.pdf
├── ctdna_bias_plots.pdf
├── ctdna_optimal_solution.zip
├── ctdna_other_solutions.zip
└── ctdna_metadata_102422.xlsx
```

## ctDNA Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.ctdna.ctdna_template.html) to see the specific metadata collected for the ctDNA assay.

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/raw/master/template_examples/ctdna_template.xlsx) to see an example of a metadata xlsx file.

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run upload command:**
```bash
cidc assays upload --assay ctdna --xlsx ctdna_metadata_102422.xlsx
```

The process will then use the metadata file to upload the required files.
