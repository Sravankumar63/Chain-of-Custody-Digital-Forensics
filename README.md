# Chain of Custody – Digital Forensics

A controlled digital-forensics project demonstrating evidence preservation, SHA-256 integrity verification, EXIF metadata analysis, secure SSH/SCP transfer, and chain-of-custody documentation.

## Environment
- Evidence source: Windows host
- Forensic workstation: Kali Linux running in QEMU
- Secure transfer: OpenSSH / SCP
- Integrity verification: SHA-256
- Metadata analysis: ExifTool 13.55
- Evidence item: `photo.png`

## Workflow
Windows evidence source → OpenSSH/SCP → Kali Linux examination copy → SHA-256 verification → ExifTool metadata analysis → chain-of-custody report.

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
│   └── project-workflow.md
├── hashes/
│   └── sha256_photo.txt
├── metadata/
│   └── exif_photo.txt
├── reports/
│   └── chain_of_custody.md
├── scripts/
│   └── forensic-commands.md
├── presentation/
│   └── README.md
└── evidence/
    └── README.md
```

## Evidence Handling
The original `photo.png` is not uploaded to this public repository. Only documentation, metadata notes, and cryptographic hash information are stored.
