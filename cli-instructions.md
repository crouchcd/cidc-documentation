#  HELLO WORLD
# The CIDC Command-Line Interface

To upload assay data to the CIDC, you will use the CIDC Command-Line Interface (CLI). For detailed guidelines on how to upload a particular assay type, browse the assay-specific documentation.

## Installation
To install the CIDC CLI, run the following command:
```bash
sudo pip3 install cidc-cli
```
## Help
To display a help message outlining the available commands for the CLI, run:
```bash
cidc
```

The default environment is set to production (`prod`). To switch to `staging` for testing purposes, run:
```bash
cidc config set-env staging
```

## Log In
Before uploading data, you'll need to log in. To do so, run:
```bash
gcloud auth login
```
```bash
cidc login [token]
```
**Note: the above line contains your valid identity token. Copy-and-paste it to log in.**

