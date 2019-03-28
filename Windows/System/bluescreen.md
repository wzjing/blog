## Q: SYSTEM_THREAD_EXCEPTION_NOT_HANDLED
## A: UnCompatable driver problem such as usb3.0 or bios configure problem. 
 1. If you can, enter safe mode and delete the latest driver you installed;.
 1. If you can go to safe mode, use conmand promot delete the latest installed driver in ***C:\windows\System32\drivers***, such as ***USBHUB3.sys***, ****.sys*** are the drivers, or you can use windows pe to do that.
 1. The pnputil tool in C:\Windows\system32 can also help you find the drivers you installed by using `C:\Windows\system32\pnputil /e`.
 1. Sometimes, you can just use `sfc /scannow` to repair thsi problem, but it will take over half an hour and maybe not work at all.