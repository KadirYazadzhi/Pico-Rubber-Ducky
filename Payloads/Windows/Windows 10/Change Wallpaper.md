# Change Wallpaper

Changes the desktop wallpaper by modifying the registry.

```
DELAY 500
GUI r
DELAY 200
STRING reg add "HKCU\\Control Panel\\Desktop" /v Wallpaper /t REG_SZ /d "C:\\path\\to\\image.jpg" /f
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.