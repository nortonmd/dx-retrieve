# sfdx force:mdapi:convert

```
Usage: sfdx force:mdapi:convert -r <directory> [-d <directory>] [--json] [--loglevel <string>] 

convert metadata from the Metadata API format into the source format

Flags:
 -d, --outputdir OUTPUTDIR  the output directory to store the source–formatted
                            files
 -r, --rootdir ROOTDIR      (required) the root directory containing the
                            Metadata API–formatted metadata
 --json                     format output as json
 --loglevel LOGLEVEL        logging level for this command invocation
                            (error*,trace,debug,info,warn,fatal)

NOTE: This command must be run from within a project.

To use Salesforce CLI to work with components that you retrieved via Metadata API, first convert your files from the metadata format to the source format using "sfdx force:mdapi:convert".

To convert files from the source format back to the metadata format, so that you can deploy them using "sfdx force:mdapi:deploy", run "sfdx force:source:convert".

Examples:
   $ sfdx force:mdapi:convert -r path/to/metadata
   $ sfdx force:mdapi:convert -r path/to/metadata -d path/to/outputdir
```
