---
title: Import
keywords: ...
last_updated:
tags: import, data
sidebar: home_sidebar
permalink: import.html
folder: IO
---

## Structure of the configuration file

The XML configuration file defines the structure of the data import files

```xml
<?xml version="1.0" encoding="UTF-8"?>
<import-config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <import>
  	<preProcess>
	  ... <!-- list of preProcesses and their options -->
  	</preProcess>
    <providers>
      ... <!-- list of providers and their options -->
    </providers>
    <actions>
      ... <!-- list of the actions activated for the import -->
    </actions>
    <consolidators>
      ... <!-- list of the consolidators activated for the import -->
    </consolidators>
    <postProcess>
    	...<!-- list of the postProcess activated for the import -->
    </postProcess>
  </import>

  <import>
    ... <!-- the description of a second import file -->
  </import>
<import-config>

```

## Pre-processing

The pre-process function allows you to preform changes to the file prior to importing

### PgpDecryption

Decrypt PGP encrypted files and move them to a specified folder

#### Fields

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`inputFolderPath` | Path to the folder containing the encrypted files. The base path is the instance's data folder | string | No 
`outputFolderPath` | Path to the folder that will contain the decrypted files.The base path is the instance's data folder | string | Yes
`signature` | Whether or not and how the encrypted file is signed | signedType | Yes | `signed`
`removeSources` | Whether or not to remove the original encrypted files after a successful decryption | yesNoElement | No | Yes

#### Example

```xml  
<preProcess>
	<pgpDecryption>
		<inputFolderPath>imports/data</inputFolderPath>
		<outputFolderPath>imports/trainings</outputFolderPath>
		<signature>signed</signature>
		<removeSources>no</removeSources>
	</pgpDecryption>
</preProcess>
```

#### Error Messages

Message | Explanation
--- | ---
`You have to set the path of GPG bin` | The path to the decryption program (GnuPG) must be defined in the instance's configuration file. You should contact the IT department.
`You have to set a public key name to encrypt data`	| The name of the client's public key must be defined in the instance's configuration file. You should contact the IT department.
`You have to set a public key ring` | The path to the public key ring must be defined in the instance's configuration file. You should contact the IT department.
`You have to set a private key ring` | The path to the private key ring must be defined in the instance's configuration file. You should contact the IT department.
`Command line [...], at least one bad signature` | At least one of the encrypted files has an invalid signature. Make sure the public key that the application uses is correct with respect to the one used to sign the encrypted files.
`Command line [...] returns an unexpected error` | An unexpected error has occured during decryption. You should contact the support department.
`Registration date is in the future` |
`Registration date is invalid` |

### Remote Resource Downloader

Download files from a distant machince via FTP, STFP or FTPS to an specified folder

#### Fields

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`protocol` | Protocol to be used for the file transfer | ftpProtocol | Yes |
`host` | Address of the distant machine from which the files will be downloaded | string | Yes |
`port` | Port of the distant machine from which the files will be downloaded | int | Yes | default is deduced by the protocol used (21 for ftp, 990 for ftps, ...)
`login` | Login used to connect to the host via the chosen protocol | string | Yes |
`password` | Password used to connect to the host via the chosen protocol with the chosen login | string | Yes |
`sourceFilesPath` | Path to the files to download from the host. Wildcards characters such as '*' are supported | string | Yes |
`destinationFolderPaht` | Path to the folder to which the files will be downloaded. The base path is the instance's data folder. | string | Yes |
`removeSources` | Whether or not to remove the files from the host once the transfer is complete | yesNoElement | No | Yes |

#### Example

```xml
<preProcess>
	<remoteResourceDownloader>
		<protocol>sFTP</protocol>
		<host>10.145.23.15</host>
		<login>user</login>
		<password>p4ssword</password>
		<sourceFilesPath>foo/bar/*.csv</sourceFilesPath>
		<destinationFolderPath>imports/</destinationFolderPath>
		<removeSouces>no</removeSouces>
	</remoteResourceDownloader>
</preProcess>

```

#### Error Messages

Message | Explanation
--- | ---
`Failed to create destination folder [...]` | The specified destination folder does not exist yet and the application failed to create it. For further information, contact the IT department.
`Failed to retrieve remote files` |	An unexpected error occured during the transfer. For further information, contact the support.
`String '..' is forbidden in file path` | For security reasons, make sure that the specified file paths do not contain the '..' string.


### Unpackager

Extracts the given archives into the specified folder. The supported formats are zip, rar, tar and tgz.

#### Fields

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`inputFilePath` | Path to the archive. Wildcard characters such as '*' are supported. | string | Yes |
`outputFilePath` | Path to the folder that will contain the files extracted from the archive | string | Yes
`removeSources` | Whether or not to remove the archive once it has been extracted | yesNoElement | No | Yes

#### Example

```xml 
<preProcess>
	<unpackager>
		<inputFilePath>imports/data/archive_*.tar</inputFolderPath>
		<outputFolderPath>imports/training/</outputFolderPath>
		<removeSources>no</removeSources>
	</unpackager>
</preProcess>

```

#### Error Messages

Message | Explanation
--- | ---
`Could not create the folder [...]` | The specified destination folder does not exist yet and the application failed to create it. For further information, contact the IT department.
`The supported archive formats are: zip, rar, tar and tgz` | The given archive has an unsupported extension.
`The archive could not be extracted` | An unexpected error has occured during the extraction. For further information, contact the support.
`String '..' is forbidden in file path`	| For security reasons, make sure that the specified file paths do not contain the '..' string.

### NatixisSecureZip

Unzip and decrypt a given zip file so that it can be processed by the import

#### Fields

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`inputFilePath` | Path to the encrypted ZIP file. The base path is the instance's data folder. | string | Yes |
`outputFilePath` | 	Path to the folder that will contain the decrypted files. The base path is the instance's data folder. | string | Yes |

#### Example

```xml 
<preProcess>
    <custom>
        <moduleName>natixis</moduleName>
        <process>NatixisSecureZip</process>
        <param name="inputFilePath">imports/encryptedData.zip</param>
        <param name="outputFolderPath">imports/</param>
    </custom>
</preProcess>
```

#### Error Messages

Message | Explanation
--- | ---
`String '..' is forbidden in input/output path folder` | References to parent directories are forbidden for security reasons.
`The input file [...] does not exists/The output folder [...] does not exists or can not be created.` | Make sure the specified file and folder do exist and that the directory permissions are correctly set.
`Impossible to copy execution data to instance folder.`	| This can mean that the process does not have sufficient right on the source code folder or the instance folder in order to copy the necessary execution data.
`Impossible to make a chmod 755 on [...] utility.` | This process needs to change permissions on certain files and folders, make sure that it is properly configured.
`No sponsor is installed, or pkzipr utility is not executable.`	| The process could not list the installed sponsors.
`Private key could not be added, maybe certificate and key are not valid or pkcerttool utility is not executable.`	| The process failed to add the private keys to the decrypting utility. Make sure the certificate is correct.
`Extraction failed, please check the file was encrypted for the right certificate.`	| Maybe the given .ZIP file in the configuration was encrypted by another sponsor.

<!-- End pre-process -->

<!-- Start providers -->
## Providers

Providers describe the setup of the type of input CSV file (eg. a file stored on the server, inside a given folder; or a file that must be retrieved through FTP)


### File System Source Provider / SFTP File Import Action

#### Fields

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`fileName` | Name of CSV file | string | Yes |
`path` | Path of the CSV file | string | No | `DATA_PATH/import`
`skipFirstLine` | Whether or not ignore the first line (because it is the header and must not be processed) | yesNoElement | Yes | Yes |
`autoDetectLineEndings` | Whether or not to automatically detect the line ending convention in the import file. This enables interoperability between Unix, Windows and Macintosh systems, but adds a small performance overhead | yesNoElement | No | No
`columnsMapping` | The columns in the CSV file, in their order of appearance | columnsMapping | Yes |
`fileEncoding` | The encoding of the CSV file | fileEncoding | No | `UTF-8` |
`delimiter` | The delimiter used in the CSV file | delimiter | No | `semicolon` |
`dateFormat` | The date format used in columns of the CSV file that contain dates | string | No | `YYYY-MM-DD`
`sftpHost` | Address of the sFTP server | string | Yes (only if retrieving from non CK FTP) |
`sftpLogin` | Login to be used for the sFTP connection | string | Yes (only if retrieving from non CK FTP)
`sftpPassword` | Password to be used for the sFTP connection | string | Yes (only if retrieving from non CK FTP)
`sftpFolder` | Path to the folder to fetch the file from. The path begins at the root folder of the supplied sFTP user. The parameter must begin with a '/' | string | Yes (only if retrieving from non CK FTP) | 	The root folder of the sFTP user on the distant server

#### Example

```xml
<providers>
	<fileSystemSourceProvider>
		<fileName>sessions_*.csv</fileName>
		<path>imports/</path>
		<skipFirstLine>no</skipFirstLine>
		<autoDetectLineEndings>yes</autoDetectLineEndings>
		<columnsMapping>
			<sessionAction>
				<createUpdate>M</createUpdate>
				<cancel>A</cancel>
			</sessionAction>
			<ignoredColumn/>
			<ignoredColumn/>
			<ignoredColumn/>
			<trainingTitle/>
			<sessionGuid/>
			<sessionStartDate/>
			<sessionEndDate/>
			<sessionStatus/>
		</columnsMapping>
		<fileEncoding>ISO-8859-1</fileEncoding>
		<delimiter>pipe</delimiter>
		<dateFormat>YYYY-MM-DD</dateFormat>
		<sftpHost>10.145.23.15</sftpHost>
		<sftpLogin>user</sftpLogin>
		<sftpPassword>p4ssword</sftpPassword>
		<sftpFolder>/folder</sftpFolder>
	</fileSystemSourceProvider>
</providers>

```

#### Error Messages

Message | Explanation
--- | ---
`[...] the given date format [...] is not valid. It should only contain the following characters (case insensitive): 'YMDHIS /_.:;,-'` | The given date format is invalid. Please make sure that is only contains the allowed characters.
`[...] unable to retrieve the file(s) from the SFTP server: error [...]` | 	The application could not retrieve the specified file from the given server.
<!-- End providers -->


<!-- Start actions -->
## Actions
Actions that are executed on each line of the CSV file. (eg. when creating the corresponding learner)

Click the links below to see detailed documentation

- [Consolidated Tracking action](/consolidated-tracking-action.html)
- [Create or Update Entity](/createorupdate-entity-action.html)
- [Create or Update Intervention](/createorupdate-intervention-action.html)
- [Create or Update Learner](/createorupdate-learner-action.html)
- [Create or Update Session](/creaateorupdate-session-action.html)
- [Create or Update Training Course](/createorupdate-trainingcourse-action.html)
- [Register Learner](/registerlearner-action.html)


<!-- End actions -->


<!-- Start consolidators -->
## Consolidators

A consolidator is a functionality that is executed at the end of each import file, after all the other actions. (eg. when moving the CSV file inside the backup folder)

In order to work properly, the consolidators must be declared in a specific order:

Click the links below to see detailed documentation

1. [`timeStampedFileErrorLogger`](/timestamped-file-error-logger-consolidator.html)`
2. [`massDisableLearners`](/mass-disable-learners-consolidator.html)
3. [`moveToBackupConsolidator`](/movetobackup-consolidator.html)
4. [`deleteOldRegistrations`](/deleteoldregistrations-consolidator.html)
5. [`deleteEmptySessions`](/delete-empty-sessions-consolidator.html)
6. [`timeLogger`](/time-logger-consolidator.html)
7. [`emailReport`](/email-report-consolidator.html)
8. [`deleteProcessedFilesConsolidator`](/delete-processed-files-consolidator.html)
9. [`removeFromSFTP`](/remove-from-sftp-consolidator.html)
10. [`cleanFolder`](/clean-folder-consolidator.html)
<!-- End consolidators -->


<!-- Start post-processing -->
## Post-processing

### Move To Backup

Used to move files from a folder to another one.

### Fields

Option | Description | Type | Mandatory | Default value
--- | --- | --- | --- | ---
`inputFolderPath` | Path to the source folder. The base path is the data folder of the instance `DATA_PATH` | string | Yes
`outputFolderPath` | Path to the destination folder. The base path is the data folder of the instance `DATA_PATH` | string | Yes
`timestamp` | Whether to prepend the timestamp to the import file when moving it to the backup folder | yesNoElement | Yes | No |

### Example

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
--- | ---
`String '..' is forbidden in in/output path folder`	| For security reasons, the string '..' is forbidden in both the inputFolder and outputFolder.
`The input folder [...] does not exists.` | The specified inputFolder does not exist.
`The output folder [...] does not exists or can not be created.` | The specified outputFolder does not exist and an unexpected error occured during its creation. This is probably a folder rights problem.
`Can not copy the file [...] to [...]` | An unexpected error occured while trying to copy the files to the destination folder. This is probably a folder rights problem.
`Can not delete the file [...]` | After successfully copying the files, the process will attempt to delete the original file, but an unexpected error occured while trying to delete it. This is probably a folder/file rights problem.
<!-- End post-processing -->




