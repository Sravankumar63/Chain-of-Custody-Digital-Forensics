# Implementation Screenshots

The implementation screenshots are maintained from the project evidence-documentation file supplied during development.

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

The screenshots document the process but the original evidence file is intentionally not published in this public repository.

The source documentation contains 37 implementation screenshots grouped under Windows and Kali sections. fileciteturn10file0L29-L32
