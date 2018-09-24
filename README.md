# av-fingerprints

This is a partial replication of results of the "[AVLeak:
Fingerprinting Antivirus Emulators Through Black-Box Testing](https://www.usenix.org/system/files/conference/woot16/woot16-paper-blackthorne_update.pdf)" paper that was presented at WOOT '16 and Black Hat USA 2016. Techniques from the paper are used to leak "fingerprints" from the x86 Windows emulators of various AV software. This can be used to develop and detect evasive malware.

Special thanks to Alexei Bulazel ([@0xAlexei](https://twitter.com/0xAlexei)) for his assistance.

| Antivirus Product | Version | Fingerprints |
|:------------------|:-------:|:-------------|
| B50C3DF2 | v13.0.3114 | 3 |

## B50C3DF2 v13.0.3114

### argv[0] value

The executable name is 6 randomly generated lower-alphabetic characters.

```
C:\Documents and Settings\Administrator\My Documents\cbfrxd.exe
C:\Documents and Settings\Administrator\My Documents\gdtfwl.exe
C:\Documents and Settings\Administrator\My Documents\kswymt.exe
C:\Documents and Settings\Administrator\My Documents\anlbux.exe
C:\Documents and Settings\Administrator\My Documents\dsjtfc.exe
```

### GetEnvironmentStrings

```
ALLUSERSPROFILE=C:\Documents and Settings\All Users
APPDATA=C:\Documents and Settings\Administrator\Application Data
CLIENTNAME=Console
CommonProgramFiles=C:\Program Files\Common Files
COMPUTERNAME=ELICZ
ComSpec=C:\WINDOWS\system32\cmd.exe
FP_NO_HOST_CHECK=NO
HOMEDRIVE=C:
HOMEPATH=\Documents and Settings\Administrator
LOGONSERVER=\\ELICZ
NUMBER_OF_PROCESSORS=2
OS=Windows_NT
Path=C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem
PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH
PROCESSOR_ARCHITECTURE=x86
PROCESSOR_IDENTIFIER=x86 Family 15 Model 4 Stepping 3, AuthenticAMD
PROCESSOR_LEVEL=15
PROCESSOR_REVISION=0403
ProgramFiles=C:\Program Files
SESSIONNAME=Console
SystemDrive=C:
SystemRoot=C:\WINDOWS
TEMP=C:\WINDOWS\Temp
TMP=C:\WINDOWS\Temp
USERDOMAIN=ELICZ
USERNAME=Administrator
USERPROFILE=C:\Documents and Settings\Administrator
windir=C:\WINDOWS
```

### GetSystemRegistryQuota

`pdwQuotaAllowed` and `pdwQuotaUsed` are not supposed to be `null`.

```
DWORD pdwQuotaAllowed = 0x00000000;
DWORD pdwQuotaUsed    = 0x00000000;
```
