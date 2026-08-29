# SBT-DF202_Practical_Lab_1_Idriss_Muhammad_Abdullahi
Name: Idriss Muhammad Abdullahi
 Course: Digital Forensics Laboratory
 Evidence Image: Ch01InChap01.dd
 Tools Used: Autopsy, The Sleuth Kit (fls, icat, blkcat, mmls, istat, md5sum, sha256sum)
 Date: 29 August 2026

1. Objective

The objective of this practical was to perform forensic analysis on the disk image Ch01InChap01.dd, identify files within the image, recover evidence, calculate integrity hashes, and document findings using accepted digital forensic procedures.

2. Chain of Custody / Evidence Documentation
Field	DetailsCase ID	DF-2026-001
Evidence ID	E001
Evidence Description	Ch01InChap01.dd
Evidence Type	Disk Image
Examiner	Idriss Muhammad Abdullahi
Purpose	Digital Forensic Investigation
Evidence Handling Log
Date	Action29-Aug-2026	Evidence image received for analysis
29-Aug-2026	Evidence loaded into Autopsy
29-Aug-2026	File system examined using TSK tools
29-Aug-2026	Recovery attempts performed
29-Aug-2026	Findings documented

3. Autopsy Case Creation and Evidence Source Configuration
Procedure
Launched Autopsy.
Created a new case.
Assigned a case name and examiner information.
Added Ch01InChap01.dd as the evidence source.
Configured the image for forensic examination.
Initiated file system analysis.
Result

The evidence image was successfully added to the case and made available.

4. Evidence Integrity Verification

Hash verification is used to ensure evidence integrity throughout the forensic process.

Commands
md5sum Ch01InChap01.dd
sha256sum Ch01InChap01.dd

The hash values generated from the source image should be recorded and maintained throughout the investigation to confirm that no modifications occurred.

5. File System Analysis

The file listing was obtained using:

fls Ch01InChap01.dd
Output
r/r 5: Client Info.mdb
r/r 8: Billing Letter.doc
r/r 11: confirmation.txt
r/r 13: Income.xls
r/r 15: letter1.txt
r/r 17: Regres.doc

6. Identification of Metadata Address

The command:
fls Ch01InChap01.dd
identified the metadata address of the target spreadsheet:

Income.xls -> Metadata Address 13

File Name	Metadata AddressIncome.xls	13
7. File Recovery Using icat

Command used
icat Ch01InChap01.dd 13 > INCOME_icat.xls

To recover the file associated with metadata address 13.

A file named:

INCOME_icat.xls
was created successfully.

8. Hash Verification of Recovered Fil
md5sum INCOME_icat.xls
sha256sum INCOME_icat.xls

MD5:
d41d8cd98f00b204e9800998ecf8427e

SHA-256:
e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
Show more lines

9. blkcat Recovery Attempt

To extract data directly from identified data blocks.

blkcat Ch01InChap01.dd <block_number> > recovered_file

10. Autopsy Keyword Search

Keyword searching functionality was successfully accessed and configured.

Keyword searching assists me in locating files and artifacts relevant to an investigation.

11. Findings i came acrosss
The image Ch01InChap01.dd was successfully analyzed.
Multiple files were identified within the file system.
The file Income.xls was located at metadata address 13.
Recovery of the file using icat produced an empty output file.
Hash values confirmed the recovered file contained no data.
Autopsy was successfully used for evidence analysis and navigation.
Forensic procedures were documented according to standard practice.
12. Conclusion

The forensic analysis of the disk image Ch01InChap01.dd was successfully conducted using Autopsy and The Sleuth Kit. File system analysis identified several files, including Income.xls, which was associated with metadata address 13. A recovery attempt using icat produced an empty file, as verified through MD5 and SHA-256 hashing. The exercise demonstrated the use of forensic tools for evidence identification, recovery attempts, integrity verification, and documentation within a digital forensic investigation.
