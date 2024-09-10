# Shells creation

Install mingw on linux
```sudo apt install mingw-w64```
```sudo apt install gcc-mingw-w64```

Download the Cwindows(not c shell code) shell code filetype: **(CWindows)** from [revsehlls.com](https://www.revshells.com/) and save it to a file windows.c than run below command it will generate a reverse shell

```i686-w64-mingw32-gcc-win32 -std=c99 windows.c -o rsh.exe -lws2_32```

#### lws2_32 this option is used to statically link binaries or else its going to produce an error
