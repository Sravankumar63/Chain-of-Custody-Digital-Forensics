# Implementation Screenshots

This folder documents the implementation screenshot sequence used during the project.

## Screenshot Sequence

1. Windows OpenSSH service and firewall configuration
2. Windows TCP/22 listening verification
3. Kali network scan and discovery of the working Windows address
4. SSH connection from Kali to Windows
5. Creation of the ChainOfCustody evidence/report/metadata directories
6. Evidence-file selection from the Windows Downloads directory
7. Copy of `photo.png` into the protected evidence directory
8. Windows SHA-256 calculation with `certutil`
9. SCP transfer of `photo.png` from Windows to Kali
10. Kali file verification and SHA-256 calculation
11. ExifTool metadata extraction
12. Final chain-of-custody report and **VERIFIED – HASH MATCHED** finding

## Evidence Handling Note

The original `photo.png` evidence file is intentionally not published in this public repository.
