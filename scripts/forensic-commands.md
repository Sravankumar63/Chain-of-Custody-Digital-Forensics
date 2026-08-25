# Forensic Commands Used

## Windows PowerShell
```powershell
Get-Service sshd
Get-NetTCPConnection -LocalPort 22 -State Listen
certutil -hashfile C:\ChainOfCustody\Evidence\photo.png SHA256
```

## Kali Linux
```bash
scp sravan@192.168.0.102:/C:/ChainOfCustody/Evidence/photo.png ~/photo.png
sha256sum ~/photo.png
exiftool ~/photo.png
```

## Integrity Check
Compare the SHA-256 value from Windows with the SHA-256 value calculated on Kali. A matching value indicates that the transferred examination copy is cryptographically consistent with the reference evidence.
