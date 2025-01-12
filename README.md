# Postmortem Hard Drive Analysis  

### Project Details  
**Team Members:**  
- Jackson Harper  
- Anthony Karlin  
- Frederic Stresau  
- Quy Pham  
- Jacob Miller  

**Course:** Digital Forensics  
**Professor:** Ujan Mukhopadhyay  
**Date:** 12/02/2024  

---

## Overview  
This project involved a postmortem analysis of a hard drive image using digital forensics tools. The goal was to recover and analyze hidden, deleted, and encrypted files while extracting metadata to infer information about the device’s usage and history.  

### Demo and Artifacts  
You can view the hard drive images here:  
[Hard Drive Images](https://drive.google.com/drive/folders/1SW6Z149WgjjpBAnK07DD3HpUFY58EcRu?usp=sharing)  

---

## Key Features of the Investigation  

### 1. Device Acquisition and Specifications  
- **Device Details:**  
  - Blue and red USB drive with a faded Superman decal.  
  - Serial Number: `067606A64090`.  
  - Formatted in FAT32, a standard for smaller storage devices.  

- **Imaging the Device:**  
  - An image of the device was created using **FTK Imager**, which allowed viewing file structures, recovering hidden/deleted files, and analyzing allocated/unallocated space.  
  - Image File: `Image01.001` (part of a split image set `.001` to `.005`).  

---

### 2. File Recovery and Analysis  

#### Tools Used:  
- **FTK Imager:** View and analyze image contents, recover hidden/deleted files.  
- **Disk Drill:** Recover deleted files from the drive.  
- **Bulk Extractor:** Extract file metadata and identify host information.  

#### Examples:  
- **Text File Recovery:**  
  - Hidden files such as *Text File 1* revealed contents like “I am going to simply hide this text file.”  
  - Deleted files such as *Text File 2* were partially recovered but showed signs of damage due to overwriting.  

- **Encrypted Files:**  
  - *Text File 3* contained encrypted Base64 data using the Blowfish algorithm. Decryption was not possible without the secret key.  
  - *Text File 4* was identified as encrypted with NTFS `PFILE` properties after converting the flash drive.  

- **PII and Media:**  
  - Recovered files included homework files, family photos, home movies, and Minecraft mod packs, belonging to a former Florida Poly student.  
  - Bulk Extractor identified sensitive data, including carved JPEGs, email addresses, phone numbers, and geolocation metadata.  

---

### 3. Host Device Identification  

#### Insights from Metadata:  
- **System Volume Information:** Confirmed usage on Windows OS hosts.  
- **Bulk Extractor Reports:**  
  - Revealed URLs, phone numbers, longitude/latitude coordinates, and directory structures.  
  - Identified common usage locations near Cincinnati, Ohio, including local schools.  

#### Challenges:  
- Determining the exact identities of connected devices was limited by the lack of detailed host metadata.  

---

## Conclusion  

This digital forensics investigation demonstrated:  
1. The ability to recover hidden, deleted, and encrypted data using tools like FTK Imager, Disk Drill, and Bulk Extractor.  
2. The challenges of incomplete recoveries due to overwriting or lack of encryption keys.  
3. The importance of leveraging multiple recovery methods to maximize investigation success.  

### Key Takeaways:  
- Digital forensics tools can reveal a wealth of information from storage devices.  
- Recovering and analyzing data requires careful handling and a multi-tool approach.  
