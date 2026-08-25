# Chain of Custody Report

## Evidence Identification
- Evidence item: `photo.png`
- Original location: `C:\ChainOfCustody\Evidence\photo.png`
- Examination copy: `/home/kali/photo.png`

## Acquisition / Transfer
The evidence was transferred from the Windows host to the Kali Linux forensic workstation using OpenSSH/SCP over the local network.

## Integrity Verification
SHA-256 reference:
`2ef665d31b00da877382e8624149ae7fc4cd8f8c907c5f6e3de8211f5094bda3`

SHA-256 examination copy:
`2ef665d31b00da877382e8624149ae7fc4cd8f8c907c5f6e3de8211f5094bda3`

**Finding: VERIFIED – HASH MATCHED**

## Metadata Examination
ExifTool 13.55 identified the evidence as a PNG image with dimensions 1254 × 1254 and approximately 1.6 MB size. Software metadata observed: `gpt-image`.

## Conclusion
The cryptographic hash of the examination copy matched the reference hash, supporting the integrity of the transferred evidence. Metadata was examined separately without modifying the evidence file.
