# av-fingerprints

This is a partial replication of results of the "[AVLeak:
Fingerprinting Antivirus Emulators Through Black-Box Testing](https://www.usenix.org/system/files/conference/woot16/woot16-paper-blackthorne_update.pdf)" paper that was presented at WOOT '16 and Black Hat USA 2016. Techniques from the paper are used to leak "fingerprints" from the x86 Windows emulators of various AV software. This can be used to develop and detect evasive malware.

Special thanks to Alexei Bulazel ([@0xAlexei](https://twitter.com/0xAlexei)) for his assistance.

| Antivirus Product | Version | Fingerprints |
|:------------------|:-------:|:-------------|
| B50C3DF2 | v13.0.3114 | 4 |

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

### CreateToolhelp32Snapshot

```
PPID    PID    Process Name
0       0      [System Process]
0       4      System
4       12     smss.exe
12      20     csrss.exe
12      28     winlogon.exe
28      36     services.exe
28      44     lsass.exe
36      52     svchost.exe
36      60     spoolsv.exe
65524   68     explorer.exe
36      76     AVP.EXE
36      84     PCCTOOL.EXE
36      92     TMPROXY.EXE
36      100    OUTPOST.EXE
36      108    VSSERV.EXE
36      116    ZAPRO.EXE
36      124    REALMON.EXE
36      132    VETMSG.EXE
36      140    VETTRAY.EXE
36      148    ZLCLIENTE.EXE
36      156    ZONEALARM.EXE
36      164    ZLCLIENT.EXE
36      172    CCAPP.EXE
36      180    CCSETMGR.EXE
36      188    CCEVTMGR.EXE
36      196    SCCOMM.EXE
36      204    CCCPROXY.EXE
36      212    NAVW32.EXE
36      220    NAVAPSVC.EXE
36      228    NPFMNTOR.EXE
36      236    CPDCLNT.EXE
36      244    PCCNTUPD.EXE
36      252    TMNTSRV.EXE
36      260    PAVPRSRV.EXE
36      268    PADMIN.EXE
36      276    PAVPROT.EXE
36      284    PANDAAV.EXE
36      292    AVENGINE.EXE
36      300    APVXDWIN.EXE
36      308    AVGUARD.EXE
36      316    AVGNT.EXE
36      324    AVSCHED32.EXE
36      332    NOD32KRN.EXE
36      340    NOD32.EXE
36      348    GBPSV.EXE
36      356    NOD32KUI.EXE
36      364    KAV.EXE
36      372    KAVMM.EXE
36      380    KAVPF.EXE
36      388    AVGEMC.EXE
36      396    AVGCC.EXE
36      404    AVGAMSVR.EXE
36      412    AVGUPSVC.EXE
36      420    AVGW.EXE
36      428    ASHWEBSV.EXE
36      436    ASHDISP.EXE
36      444    ASHMAISV.EXE
36      452    ASHSERV.EXE
36      460    ASHUPDSV.EXE
36      468    EWIDOCTRL.EXE
36      476    GUARD.EXE
36      484    GCASDTSERV.EXE
36      492    MSMPENG.EXE
36      500    MCAFEE.EXE
68      508    iexplore.exe
68      516    firefox.exe
68      524    opera.exe
68      532    safari.exe
68      936    vzrbaa.exe
68      936    jtpyzc.exe
68      936    pukfco.exe
68      936    twyzmg.exe
68      936    jtbtwy.exe
68      936    and so on...
```

### GetSystemRegistryQuota

`pdwQuotaAllowed` and `pdwQuotaUsed` are not supposed to be `null`.

```
DWORD pdwQuotaAllowed = 0x00000000;
DWORD pdwQuotaUsed    = 0x00000000;
```
