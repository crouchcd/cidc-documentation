# The CIDC Command-Line Interface

To upload assay data to the CIDC, you will use the CIDC Command-Line Interface (CLI). For detailed guidelines on how to upload a particular assay type, browse the assay-specific documentation.

## Installation
To install the CIDC CLI, run the following command:
```bash
pip3 install cidc-cli
```
## Help
To display a help message outlining the available commands for the CLI, run:
```bash
cidc
```
## Log In
Before uploading data, you'll need to log in. To do so, run:
```bash
cidc login [token]
```
**Note: the above line contains your valid identity token. Copy-and-paste it to log in.**
