Man in Browser Hooking using API hooking and DLL injection
==============================
DLL file present  in the provided zip (password-infected)
When you start internet explorer on Windows 10, Automaticall start edge(as most sites compatible with edge). Disable the BHO that is responsible for the redirection.
follow- https://www.youtube.com/watch?v=ERDkAhHw50M

We need to inject DLL(hookdll.dll) into internet explorer(C:\Program Files (x86)\Internet Explorer), so need to disable the redirection of internet Explorer to Edge

1)The DLL hooks InternetReadFile() API in Internet Explorer 32 bit version
2)Inject the Hook.dll into internet explorer(32 bit ) using RemoteDLL Tool https://securityxploded.com/remotedll.php
3)Browse the pages
