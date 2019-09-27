---
title: Export
keywords: ...
last_updated: December 14, 2016
tags:
sidebar: home_sidebar
permalink: export.html
folder: IO
---

## Structure of the configuration file

The XML configuration file defines the structure of the data export files

```xml
<?xml version="1.0" encoding="UTF-8"?>
<export-config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <export>
    	<providers>
    		<!-- Data export column and parameter definitions should be added here -->
        </providers>
        <actions>
        	<!-- Data export actions should be added here -->
        </actions>
        <consolidators>
            <moveToFolder>
                <fileName>file_name.csv</fileName>
                <folderPath>/var/www/instance/data/export/</folderPath>
            </moveToFolder> 
        </consolidators>
    </export>
</export-config>

```

## Actions

### File export action

File export action allows to create a temporary file with the data from the chosen provider.

{:.optionsTable}
Option | Description | Mandatory | Allowed values | Default value
--- | --- | --- | --- 
`format` | Format of the temporary file | No | CSV, TSV, XML, XLS | `CSV`
`encoding` | Encoding of the temporary file | No | UTF-8, ISO-8859-1, WINDOWS-1252, UTF-16LE | `UTF-8`
`delimiter` | The delimiter to be used in the temporary file to separate the columns | No | comma, pipe, semicolon, tabulation | `semicolon`
`showHeaders` | Whether or not to write the column headers to the temporary file | No | yes, no | `yes`
`decimal` | The decimal separator to be used in the temporary file | No | comma, point | `point`

For example, the following configuration will write the data given by the provider to a temporary CSV file, using UTF-8 encoding, semicolon delimiter and include column headers.

```xml
<actions>
	<fileExportAction>
		<format>CSV</format>
		<encoding>UTF-8</encoding>
		<delimiter>semicolon</delimiter>
		<showHeaders>yes</showHeaders>
	</fileExportAction>
</actions>
```

### SFTP export action

SFTP export action allows to create a temporary data file and upload it via sFTP to a remote server.

{:.optionsTable}
Option | Description | Mandatory | Allowed values | Default value
--- | --- | --- | ---
`format` | Format of the temporary file | No | CSV, TSV, XML, XLS | `CSV`
`encoding` | Encoding of the temporary file | No | UTF-8, ISO-8859-1, WINDOWS-1252, UTF-16LE | `UTF-8`
`delimiter` | The delimiter to be used in the temporary file to separate the columns | No | comma, pipe, semicolon, tabulation | `semicolon`
`showHeaders` | Whether or not to write the column headers to the temporary file | No | yes, no | `yes`
`decimal` | The decimal separator to be used in the temporary file | No | comma, point | `point`
`sftpHost` | Address of the sFTP server. | Yes | - | 
`sftpLogin` | Login to be used for the sFTP connection. | Yes | - | 
`sftpPassword` | Password to be used for the sFTP connection. |	Yes | - | 
`sftpFolder` | Path to the folder to fetch the file from. The path begins at the root folder of the supplied sFTP user. The parameter must begin with a '/'. | Yes | - |
`fileName` | Full name to be given to the file (with extension) when it is uploaded to the remote server. See Additional string formats | Yes | - | 	

The following configuration will temporarily write the data given by the provider to a temporary CSV file, encoded using UTF-8, with semicolons as delimiters, with the column headers and using a '.' as the decimal separator. The file will then be uploaded to a specific folder on `10.145.23.15` with the following name: `temp_data_{day}_{month}_{year}.csv`.

```xml
<actions>
	<sftpExportAction>
		<format>CSV</format>
		<encoding>UTF-8</encoding>
		<delimiter>semicolon</delimiter>
		<showHeaders>yes</showHeaders>
		<decimal>point</decimal>
		<sftpHost>10.145.23.15</sftpHost>
		<sftpLogin>user</sftpLogin>
		<sftpPassword>p4ssword</sftpPassword>
		<sftpFolder>/folder</sftpFolder>
		<fileName>temp_data_%d_%m_%y.csv</fileName>
	</sftpExportAction>
</actions>
```

## Consolidators

In order to work properly, the consolidators must be declared in a specific order:
1. `timeLogger`
1. `moveToFolder`
1. `emailReport`
1. `archive`
1. `generateEndFile`
1. `cleanFolder`

### Time logger

Internal processor which computes the time spent by each part of the export, to display this time spent in the scheduled task logs.


### Move to folder

Move the temporary export files to the specified folder, with a given filename format.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`fileName` | The filename format for the export files after they have been moved. | Yes | No default value
`folderPath` | Path to the folder where the files will be moved to. No base path, a full path must be given. | Yes | No default value
`deleteEmptyFiles` | If specified, empty exports files will be deleted. | No | `no`

The following consolidator will move the export files to `/var/www/instance/data/exports/`.
The export files will be renamed with respect to the following format: `export_{day}_{month}_{year}_{number of iteration}.csv`.

```xml
<consolidators>
	<moveToFolder>
		<filename>export_%d_%m_%y_%i.csv</filename>
		<folderPath>/var/www/instance/data/exports/</folderPath>
		<deleteEmptyFiles>yes</deleteEmptyFiles>
	</moveToFolder>
</consolidators>
```

Error messages

Message | Explanation
---- | ----
`The [...] parameter is missing.` | One of the mandatory parameters is empty.
`Unable to access the export temp file: [...]` | An unexpected error occured while trying to access the temporary export files. This is probably a folder/file rights problem.
`Unable to copy the destination file: [...]` | An unexpected error occured while trying to copy the temporary export files. This is probably a folder/file rights problem.

### Email report

An email can be sent to a list of email addresses at the end of the task. In addition to the link to download the error log file, another link that enables the user to download the export file is also included in the e-mail.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`targetEmail` | Full path to the folder that will contain the old export files. There is no base path, the full path must be given. | No |
`includeDownloadLink` | Wether the email's body needs to include a download link. | No | no

```xml
<consolidators>
	<emailReport>
		<targetEmail>mmouse@wiley.com</targetEmail>
		<includeDownloadLink>yes</includeDownloadLink>
	</emailReport>
</consolidators>
```

### Archive

Move all export files to a specified folder, except the last exported file.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`folderPath` | Full path to the folder that will contain the old export files. There is no base path, the full path must be given. | No | `DATA_PATH/exports/archive/`
`prefix` | Prefix to identify the export files.	| No | No default value

The following consolidator will move all the old export files (files that begin with 'export_') to `/var/www/instance/data/exports/archive/`.

```xml
<consolidators>
	<archive>
		<folderPath>/var/www/instance/data/exports/archive/</folderPath>
		<prefix>export_</prefix>
	</archive>
</consolidators>
```

Message | Explanation
---- | ----
`The [...] parameter is missing.` | One of the mandatory parameters is empty.
`Unable to access the export temp file: [...]` | An unexpected error occured while trying to access the temporary export files. This is probably a folder/file rights problem.
`Unable to copy the destination file: [...]` | An unexpected error occured while trying to copy the temporary export files. This is probably a folder/file rights problem.

### Generate end file

This consolidator creates a file when the export process is complete.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`fileName` | The filename format for the end file. | Yes | No default value
`folderPath` | Path to the folder where the end file will be written. No base path, a full path must be given. | Yes |No default value
`fileContent` | Content of the end file. | Yes |No default value

The following consolidator will write a certain message to the specified file one the export is done.
The end file will be named in the following format: `export_end_file_{day}_{month}_{year}.csv`.

```xml
<consolidators>
	<generateEndFile>
		<filename>export_end_file_%d_%m_%y.csv</filename>
		<folderPath>/var/www/instance/data/exports/</folderPath>
		<fileContent>The export is done.</fileContent>
	</generateEndFile>
</consolidators>
```

Message | Explanation
---- | ----
`The [...] parameter is missing.` | One of the mandatory parameters is empty.
`Unable to create the destination file: [...]` | An unexpected error occured while trying to create the end file. This is probably a folder/file rights problem.

### Clean folder

Similar to the CleanFolder consolidator for imports, this consolidator cleans the data in the specified folder, as well as log files (`in DATA_PATH/exports/logs`) if needed. It is possible to specify a number of days beyond which the data is considered obsolete and thus will be removed.


Option | Description | Mandatory | Default value
--- | --- | --- | ---
`dataFolderPath` | Path to the folder containing the data to be cleaned. The base path is `DATA_PATH` (the data folder of the instance). | No | No default value
`cleanLogs` | Whether or not to clean the log folder, which is `DATA_PATH/exports/logs` | No | `no`
`cleanOlderThan` | If specified, only clean data that is older than the number of days given in this option. | No | `30`


The following consolidator will delete both log files (in `DATA_PATH/exports/logs`) and data files (`DATA_PATH/exports/data`) that are more than 2 weeks old.

```xml
<consolidators>
	<cleanFolder>
		<dataFolderPath>exports/data</dataFolderPath>
		<cleanLogs>yes</cleanLogs>
		<cleanOlderThan>14</cleanOlderThan>
	</cleanFolder>
</consolidators>
```

Message | Explanation
---- | ----
`Folder : [...] doesn't exist or isn't a directory.` | The folder specified in dataFolderPath is not a folder or does not exist.


## Post-processing

### Move to backup

Moves files from a folder to another one.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`inputFolderPath` | Path to the source folder. The base path is the data folder of the instance `DATA_PATH`. | Yes | No default value
`outputFolderPath` | Path to the destination folder. The base path is the data folder of the instance `DATA_PATH`. | Yes | No default value
`timestamp` | Whether to prepend the timestamp to the import file when moving it to the backup folder. | No | `no`


The following consolidator will move all the files from `DATA_PATH/imports/source` to `DATA_PATH/imports/destination`, prepending the timestamp to the filenames while moving them.

```xml
<postProcess>
	<moveToBackup>
		<inputFolderPath>imports/source/</inputFolderPath>
		<outputFolderPath>imports/destination/</outputFolderPath>
		<timestamp>yes</timestamp>
	</moveToBackup>
</postProcess>
```

Message | Explanation
---- | ----
`String '..' is forbidden in in/output path folder` | For security reasons, the string '..' is forbidden in both the inputFolder and outputFolder.
`The input folder [...] does not exists.` | The specified inputFolder does not exist.
`The output folder [...] does not exists or can not be created.` | The specified outputFolder does not exist and an unexpected error occured during its creation. This is probably a folder rights problem.
`Can not copy the file [...] to [...]` | An unexpected error occured while trying to copy the files to the destination folder. This is probably a folder rights problem.
`Can not delete the file [...]` | After successfully copying the files, the process will attempt to delete the original file, but an unexpected error occured while trying to delete it. This is probably a folder/file rights problem.

### Package files

Compress the exported files into an archive. The supported formats are `zip`, `rar`, `tar` and `tgz`.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`type` | The archive format. | Yes | No default value
`inputFolderPath` | Path to the folder containing the files to be archived. The base path is the data folder of the instance `DATA_PATH`. | Yes | No default value
`outputFilePath` | Path to the output file (the resulting archive), without the extension. Date formats are supported in this parameter. The base path is the data folder of the instance `DATA_PATH`. | Yes | No default value
`removeSources` | Whether or not to remove the original files once they have been archived.	| No | `yes`

```xml
<postProcess>
	<packager>
		<type>tar</type>
		<inputFolderPath>exports/files</inputFolderPath>
		<outputFilePath>exports/archive.tar</outputFilePath>
		<removeSources>no</removeSources>
	</packager>
</postProcess>
```


Message | Explanation
---- | ----
`The input folder [...] does not exists.` | The folder specified in inputFolderPath does not exist, so the post-process cannot find the files to archive.
`The output folder [...] does not exists or can not be created.` | The specified destination folder does not exist yet and the application failed to create it. This is probably a folder rights problem.
`The package couldn't be built.` | An unexpected error has occured during the compression. For further information, contact the support.
`String '..' is forbidden in file path` | For security reasons, make sure that the specified file paths do not contain the '..' string.


### Encryption

This allows to encrypt files with PGP and move the encrypted files to the specified folder. Be careful, if you use both: post process packager and PGP encryption (`clearsigned` and `signed` method) you may not be able to unzip the file.


Option | Description | Mandatory | Default value
--- | --- | --- | ---
`inputFolderPath` | Path to the folder containing the files to encrypt. The base path is the instance's data folder. | Yes | No default value
`outputFolderPath` | Path to the folder that will contain the decrypted files. The base path is the instance's data folder. | Yes | No default value
`signature` | Whether or not and how the file will be signed. | No | `signed`
`removeSources` | Whether or not to remove the original encrypted files after a successful decryption. | No | `no`

```xml
<postProcess>
	<pgpEncryption>
		<inputFolderPath>imports/files/</inputFolderPath>
		<outputFolderPath>imports/encrypted/</outputFolderPath>
		<signature>signed</signature>
		<removeSources>no</removeSources>
	</pgpEncryption>
</postProcess>
```

Message | Explanation
---- | ----
`You have to set the path of GPG bin` | The path to the decryption program (GnuPG) must be defined in the instance's configuration file. You should contact the IT department.
`You have to set a public key name to encrypt data` | The name of the client's public key must be defined in the instance's configuration file. You should contact the IT department.
`You have to set a public key ring` | The path to the public key ring must be defined in the instance's configuration file. You should contact the IT department.
`You have to set a private key ring` | The path to the private key ring must be defined in the instance's configuration file. You should contact the IT department.
`Command line [...] returns an unexpected error` | An unexpected error has occured during encryption. You should contact the support department.

### Remote resource uploader

Upload files to a specified folder on a remote directory via FTP, FTPS or SFTP.

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`protocol` | Protocol to be used for the file transfer.	| Yes | No default value
`host` | Address of the distant machine from which the files will be downloaded. | Yes | No default value
`port` | Port of the distant machine from which the files will be downloaded. | No | Default is deduced by the protocol used (21 for FTP, 990 for FTPS, ...)
`login` | Login used to connect to the host via the chosen protocol. | Yes | No default value
`password` | Password used to connect to the host via the chosen protocol with the chosen login. | Yes | No default value
`sourceFilesPath` | Path to the files to upload to the host. Wildcards characters such as '*' are supported. The base path is the instance's data folder. | Yes | No default value
`destinationFolderPath` | Path to the folder on the distant machine to which the files will be uploaded. The base path is the root folder of the supplied FTP/FTPS/sFTP user. | Yes | No default value	
`removeSources` | Whether or not to remove the original files once the transfer is complete. | No | `yes`

```xml
<postProcess>
	<remoteResourceUploader>
		<protocol>sFTP</protocol>
		<host>10.145.23.15</host>
		<login>user</login>
		<password>p4ssword</password>
		<sourceFilesPath>imports/*.csv</sourceFilesPath>
		<destinationFolderPath>foo/bar/</destinationFolderPath>
		<removeSouces>no</removeSouces>
	</remoteResourceUploader>
</postProcess>
```

Message | Explanation
---- | ----
`Failed to upload files to remote server` | An unexpected error occured during the transfer. For further information, contact the support.
`String '..' is forbidden in file path` | For security reasons, make sure that the specified file paths do not contain the '..' string.


### CallBack Url

Perform a HTTP request on a specific URL when the export is completed (`GET` or `POST`).

Option | Description | Mandatory | Default value
--- | --- | --- | ---
`url` | URL to call. | Yes | No default value
`method` | Protocol to be used for the file transfer. | No | GET
`joinFileList` | Detailed configuration of files and folders to list in the data sent in the request. | No | No default value
`fields` | Data fields to send back in the URL. | No | No default value


```xml
<postProcess>
	<callBackUrl>
		<url>www.google.com</url>
		<method>POST</method>
		<joinFileList>
            <folderPath>folder1</folderPath> <!-- Name of one folder where to search files -->
            <fieldName>field1</fieldName> <!-- GET/POST fieldname where to send the list of files for this folder -->
        </joinFileList>
		<joinFileList>
            <folderPath>folder3</folderPath> <!-- Name of one folder where to search files -->
            <fieldName>field3</fieldName> <!-- GET/POST fieldname where to send the list of files for this folder -->
        </joinFileList>
        <fields>
            <field>
                <name>client</name>
                <value>disney</value>
            </field>
            <field>
                <name>export</name>
                <value>export-02</value>
            </field>
        </fields>
	</callBackUrl>
</postProcess>
```

### HRIS Export

Enable HRIS/OCN connector for this export.

```xml
<postProcess>
    <HRISExportPostProcess>
        <type>SUCCESSFACTOR</type>
    </HRISExportPostProcess>
</postProcess>
```