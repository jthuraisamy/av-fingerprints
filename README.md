# av-fingerprints

This is a partial replication of results of the "[AVLeak:
Fingerprinting Antivirus Emulators Through Black-Box Testing](https://www.usenix.org/system/files/conference/woot16/woot16-paper-blackthorne_update.pdf)" paper that was presented at WOOT '16 and Black Hat USA 2016. Techniques from the paper are used to leak "fingerprints" from the x86 Windows emulators of various AV software. This can be used to develop and detect evasive malware.

Special thanks to Alexei Bulazel ([@0xAlexei](https://twitter.com/0xAlexei)) for his assistance.

|   | [B50C3DF2 (v13.0.3114)](B50C3DF2.md) | A3150A5E (v18.6.3983.0) | [949A2A6D (v4.00.09)](949A2A6D.md) |
|:--|:---------------------:|:-----------------------:|:-------------------:|
| **Environmental Artifacts** | 3 | 0 | 1 |
| **OS API Inconsistency**    | 1 | 0 | 0 |
| **Network Emulation**       | 0 | 0 | 0 |
| **Timing**                  | 0 | 0 | 0 |
| **Process Introspection**   | 0 | 0 | 0 |
| **CPU “Red Pills”**         | 0 | 0 | 0 |
