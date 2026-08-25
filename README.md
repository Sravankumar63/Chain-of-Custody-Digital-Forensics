# Chain of Custody – Digital Forensics

A controlled digital-forensics project demonstrating evidence preservation, SHA-256 integrity verification, EXIF metadata analysis, secure SSH/SCP transfer, and chain-of-custody documentation.

## Architecture

```text
┌──────────────────────────────┐
│ Windows Host                 │
│ Evidence Source: photo.png   │
│ OpenSSH Server / TCP 22      │
└──────────────┬───────────────┘
               │ SSH / SCP
               ▼
┌──────────────────────────────┐
│ Kali Linux in QEMU           │
│ Forensic Examination System   │
└──────────────┬───────────────┘
               │
       ┌───────┴────────┐
       ▼                ▼
┌──────────────┐  ┌──────────────┐
│ SHA-256      │  │ ExifTool     │
│ Integrity    │  │ Metadata     │
│ Verification │  │ Examination  │
└──────┬───────┘  └──────┬───────┘
       └───────┬─────────┘
               ▼
┌──────────────────────────────┐
│ Chain-of-Custody Report      │
│ Finding: VERIFIED – HASH     │
│ MATCHED                      │
└──────────────────────────────┘
```

A detailed version is available in [`docs/architecture.md`](docs/architecture.md).

## Environment

- Evidence source: Windows host
- Forensic workstation: Kali Linux running in QEMU
- Secure transfer: OpenSSH / SCP
- Integrity verification: SHA-256
- Metadata analysis: ExifTool 13.55
- Evidence item: `photo.png`

## Workflow

Windows evidence source → OpenSSH/SCP → Kali Linux examination copy → SHA-256 verification → ExifTool metadata analysis → chain-of-custody report.

## Implementation Steps

1. Configure and start the Windows OpenSSH Server.
2. Enable the inbound TCP/22 firewall rule.
3. Identify the reachable Windows IP address.
4. Verify TCP/22 from Kali.
5. Establish an SSH session from Kali to Windows.
6. Create separate Evidence, Reports, and Metadata directories.
7. Select the evidence file and copy it into the evidence directory.
8. Calculate the Windows SHA-256 reference hash.
9. Transfer the evidence copy to Kali using SCP.
10. Calculate the SHA-256 of the Kali examination copy.
11. Compare the hashes.
12. Extract metadata with ExifTool.
13. Record the findings and processing time in the chain-of-custody report.

## Result

Recorded SHA-256 for `photo.png`:

`2ef665d31b00da877382e8624149ae7fc4cd8f8c907c5f6e3de8211f5094bda3`

The Windows reference hash and Kali examination-copy hash matched: **VERIFIED – HASH MATCHED**.

## Metadata Summary

- File type: PNG
- Image dimensions: 1254 × 1254 pixels
- File size: approximately 1.6 MB
- Metadata tool: ExifTool 13.55
- Software metadata observed: `gpt-image`

## Project Structure

```text
.
├── README.md
├── docs/
│   ├── architecture.md
│   └── project-workflow.md
├── evidence/
│   └── README.md
├── hashes/
│   └── sha256_photo.txt
├── metadata/
│   └── exif_photo.txt
├── reports/
│   └── chain_of_custody.md
├── scripts/
│   └── forensic-commands.md
├── screenshots/
│   └── README.md
└── presentation/
    └── README.md
```

## Screenshots

The implementation screenshot sequence is documented in [`screenshots/README.md`](screenshots/README.md). It covers the Windows OpenSSH setup, network verification, SSH/SCP acquisition, SHA-256 verification, ExifTool analysis, and final integrity finding.

## Evidence Handling

The original `photo.png` is not uploaded to this public repository. Only documentation, metadata notes, and cryptographic hash information are stored.
