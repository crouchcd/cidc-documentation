# TCRseq

T-cell receptor sequencing (TCRseq) is an extension of RNAseq that uses a mix of primers specific for the TCR to study the diversity of these receptors. As T cells are highly important in cell-based immunity, describing their varieties and distribution provides a window into the function of the adaptive immune system.

## TCRseq Workflow Overview

1. The CIMAC technician who is performing the experiment downloads a copy of the TCRseq metadata spreadsheet template via the CIDC portal.
2. The CIMAC technician begins populating the metadata spreadsheet. **NOTE:** If the biospecimens have not yet been relabled to use CIMAC IDs, then the technician should *digitally* re-label the samples by replacing the native identifiers with the CIMAC ID when loading the samples into the machine.
3. The CIMAC technician performs the experiment and data analysis.
3. The CIMAC technician performs the experiment and data analysis.
4. The CIMAC technician or CIMAC bioinformatics support fills in the columns of the metadata spreadsheet.
5. The CIMAC technician or CIMAC bioinformatics support transfers the metadata and the data files to a CIDC upload bucket, following the concierge model.
6. The CIDC engineer transfers the metadata and the data files to CIDC using the command line tool.

## TCRseq Files

Example directory for TCR MiSeq fastq data transfer:
```
.
├── read1.fastq.gz
├── read2.fastq.gz
├── index1.fastq.gz
├── index2.fastq.gz
├── sample_sheet.csv
├── TCRseq_metadata_30012020.xlsx
```

Example directory for TCR MiSeq adaptive data transfer:
```
.
├── reads.tsv
├── sample_sheet.csv
├── TCRseq_metadata_30012020.xlsx
```

## TCR Metadata

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.tcr.tcr_fastq_template.html) to see the specific metadata collected for the TCRseq assay (FASTQ format).

Click [here](https://cimac-cidc.github.io/cidc-schemas/docs/assays.tcr.tcr_adaptive_template.html) to see the specific metadata collected for the TCRseq assay (Adaptive format).


Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/tcr_fastq_template.xlsx) to see an example of a metadata xlsx file (FASTQ format).

Click [here](https://github.com/CIMAC-CIDC/cidc-schemas/blob/master/template_examples/tcr_adaptive_template.xlsx) to see an example of a metadata xlsx file (Adaptive format).

## Uploading Files

**Start the CLI and use your Identity Token (displayed below) to log in**
```bash
cidc login [token]
```

**Run Assay-upload command, specifying the format as fastq:**
```bash
cidc assays upload --assay tcr_<format> --xlsx tcr_metadata_20201005.xlsx
```

The process will then use the metadata file to upload the required files. The files can be viewed on the portal [here](https://stagingportal.cimac-network.org/browse-files) once the upload is complete.
