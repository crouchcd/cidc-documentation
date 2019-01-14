## Before uploading data
If you haven't already, see our instructions on downloading and installing the CIDC-CLI which you will use to upload data.

[CIDC-CLI Install Instructions](https://stagingportal.cimac-network.org/portal/cimac_biofx/cli-install)

You also need to install the Google Cloud SDK.

[Google Cloud SDK](https://cloud.google.com/sdk/install)

After installation you'll need to authenticate the SDK with the following command. Use the credentials you created for this portal.

```console
$ gcloud auth application-default login
```

## Whole Exome Sequencing (WES) File Type

Our WES upload process expects the upload of a metadata file.

Meta Data file is a csv file and requires following columns:
- Columns
- SAMPLE_ID
- TRIAL_ID
- PATIENT_ID
- TIMEPOINT
- TIMEPOINT_UNIT
- FASTQ_NORMAL_1
- FASTQ_NORMAL_1
- FASTQ_TUMOR_1
- FASTQ_TUMOR_1
- BATCH_ID
- INSTRUMENT_MODEL
- READ_LENGTH
- AVG_INSERT_SIZE

## Uploading Files

Start the CLI and use your JWT to log in

```console
(Cmd) jwt_login ey927853.......
```
