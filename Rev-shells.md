# Shells creation

Install mingw on linux
```sudo apt install gcc-mingw-w64```

Download the c shell code(CWindows) from [revsehlls.com](https://www.revshells.com/) and save it to a file windows.c than run below command it will generate a reverse shell

```i686-w64-mingw32-gcc-win32 -std=c99 windows.c -o rsh.exe -lws2_32```
