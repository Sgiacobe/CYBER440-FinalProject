# Memory Analysis

Memory dumps analyzed using Volatility

### IT_2

- OS: Windows 7 Service Pack 1 64-bit
- Profile: --profile=Win7SP1x64
- Date/Time: 2020-03-01 19:54:10 UTC+0000

#### pslist - Interesting Services

- MRCv120.exe: Seen in DiskAnalysis.md. What does it do?
- thunderbird.ex: Mail service? I thought this was MacOS proprietary? **this is a software component to Mozilla Firebird. Allows for open source chat client, news feed reader, and email client. Non-essential**

---

### Mayor1_3

- OS: Windows 7 Service Pack 1 64-bit
- Profile: --profile=Win7SP1x64
- Date/Time: 2020-03-02 21:48:57 UTC+0000

#### pslist - Interesting Services

- MRCv120.exe: Seen in DiskAnalysis.md. What does it do?
- thunderbird.ex: Mail service? I thought this was MacOS proprietary? **this is a software component to Mozilla Firebird. Allows for open source chat client, news feed reader, and email client. Non-essential**
- dwm.exe: What is it? **this is "Desktop Window Manager"**
- svchost.exe: More than normal
- iexplore.exe: High usage

---

### Mayor1_4

- OS: Windows 7 Service Pack 1 64-bit
- Profile: --profile=Win7SP1x64
- Date/Time: 2020-03-03 17:58:12 UTC+0000

#### pslist - Interesting Services

- MRCv120.exe: Seen in DiskAnalysis.md. What does it do?
- thunderbird.ex: Mail service? I thought this was MacOS proprietary? **this is a software component to Mozilla Firebird. Allows for open source chat client, news feed reader, and email client. Non-essential**
- dwm.exe: What is it? **this is "Desktop Window Manager"**
- svchost.exe: More than normal

---

### Mayor2_3

- OS: Windows 7 Service Pack 1 64-bit
- Profile: --profile=Win7SP1x64
- Date/Time: 2020-03-02 22:01:10 UTC+0000

#### pslist - Interesting Services

- Similar to previous Mayor hosts

---

### Mayor2_4

- OS: Windows 7 Service Pack 1 64-bit
- Profile: --profile=Win7SP1x64
- Date/Time: 2020-03-03 17:58:51 UTC+0000

#### pslist - Interesting Services

- MRCv120.exe: Seen in DiskAnalysis.md. What does it do?
- thunderbird.ex: Mail service? I thought this was MacOS proprietary? **this is a software component to Mozilla Firebird. Allows for open source chat client, news feed reader, and email client. Non-essential**
- dwm.exe: What is it? **this is "Desktop Window Manager"**
- svchost.exe: More than normal

#### hashdump - Cracking Passwords
 - Administrator: LIVERPO

---

### WinServer_1
- OS: Windows 2016 Server 64-bit
- Profile: --profile=Win2016x64_14393
- Date/Time: 2020-02-28 16:50:33 UTC+0000

#### pslist - Interesting Services

- svchost.exe: More than normal
- hMailServer.ex: Mail server?
- ismserv.exe: What's this? **Microsoft Server Intersite Messaging - needed for PC to work properly**
- dns.exe: DNS server? **file.net says it to be a trustworthy file from Microsoft. It uses ports to connect to/from a LAN or the internet**

---

### WinServer_3
- OS: Windows 2016 Server 64-bit
- Profile: --profile=Win2016x64_14393
- Date/Time: 2020-03-02 22:03:27 UTC+0000

#### pslist - Interesting Services

- spaceman.exe: _Explore this process for malicious activity_
- unsecapp.exe: _Explore this process for malicious activity_
- Other services similar to WinServer_1
