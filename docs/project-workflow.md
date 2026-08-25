# Project Workflow

## Objective
Demonstrate a simple, auditable chain of custody for one digital evidence item using only the selected tools: OpenSSH/SCP, SHA-256, and ExifTool.

## Step 1 – Prepare Evidence Repository
On the Windows host:
```powershell
mkdir C:\ChainOfCustody
mkdir C:\ChainOfCustody\Evidence
mkdir C:\ChainOfCustody\Reports
mkdir C:\ChainOfCustody\Metadata
```

## Step 2 – Secure Remote Access
OpenSSH Server was enabled on Windows and configured to run automatically. Port 22 was confirmed listening. Kali reached the Windows host at `192.168.0.102`.

## Step 3 – Transfer Evidence
The selected evidence file was copied into the Windows evidence directory and transferred to Kali using SCP:
```bash
scp sravan@192.168.0.102:/C:/ChainOfCustody/Evidence/photo.png ~/photo.png
```

## Step 4 – SHA-256 Integrity Verification
Windows produced the reference SHA-256 using `certutil`. Kali calculated the SHA-256 using `sha256sum`. The values matched.

Reference hash:
`2ef665d31b00da877382e8624149ae7fc4cd8f8c907c5f6e3de8211f5094bda3`

Result: **VERIFIED – HASH MATCHED**.

## Step 5 – EXIF Metadata Examination
ExifTool 13.55 was used on Kali to inspect the examination copy. Relevant findings included PNG format, 1254 × 1254 dimensions, approximately 1.6 MB size, and software metadata `gpt-image`.

## Step 6 – Chain-of-Custody Report
The evidence name, original Windows path, hash, metadata findings, and processing timestamp were recorded in the report.

## Evidence Principle
The original evidence is kept outside the public GitHub repository. The repository stores reproducible documentation and cryptographic verification information, not the private evidence file itself.
