# TAK Client Autoenroll Mission Package

## Purpose

This package is used in conjunction with a TAK Server that is configured for Certificate autoenrolment. Either through a Microsoft Certificate Authority or using the built in TAK Server CA. 

## Installation

### Preparation

- Clone the repository to your computer
- Add your truststore (in P12 format) to the root directory of the clone
- Edit the MANIFEST/manifest.xml file with a text editor
- Locate this line `<Content ignore="false" zipEntry="truststore.p12"/>` and change the truststore.p12 to the filename of your truststore file
- Save your changes and close the editor
- Zip the entire directory, ensuring you zip the root directory and the MANIFEST directory. Do not zip the folder that contains the clone
- Copy the newly created zip file to your ATAK or WINTAK device

### Fresh ATAK Installation

- The first time you start ATAK you will be shown a TAK Device Setup Box
- Select Data Package and then locate the zip file that you copied across
- You will then be prompted for the Username and Password for your TAK Server User Account enter those and your device will then go through the enrollment process
- Once completed you will be given a successful message and you will now be online

### Existing ATAK Installation

- Open up the additional menu and locate the Import Tool and tap on that
- Select Local SD
- Locate the zip file that you've copied across and tap on that
- You will then be prompted for the Username and Password for your TAK Server User Account enter those and your device will then go through the enrollment process
- Once completed you will be given a successful message and you will now be online
- If you had an existing TAK Server configured it will still be setup and connected. You will need to manually remove that if it's no longer required

### Adding additional files to the Mission Package

You can add additional files to this mission package to make the provisioning of new devices streamlined. Things such as map sources, saved mapping and even Plugins can be added to the mission package. 

To add a file simply:
- Copy the file into the root of the clone
- Edit the MANIFEST/manifest.xml file with a text editor
- Locate the `<contents>` section of the xml
- Add an additional line below the truststore entry `<Content ignore="false" zipEntry="Filename.ext"/>`
- Zip the MP and copy to your device

On importing this MP ATAK and WINTAK will know what to do with the various files and move them to the correct locations.
