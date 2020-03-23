# Status Report 1
Team 1
  - Brant Goings: **Network, Disk, Memory, Logs, BLUF**
  - Sarah Hume: **Logs**
  - Ryan Coe: **Disk**
  - Stephen Giacobe: **BLUF**
  - Parker Chambers: **Disk**
  - Matt Mineo: **Memory**

### Data Description BLUF

The client provided our team with about four days of network traffic data, nine disk images, seven memory dumps, and about 90,000 log events. All of this data resides within the client's LAN.

Network analysis shows frequent traffic travelling between 192.168.100.10 and all other hosts on the network. We speculate this is the Domain Controller.

When analyzing the disk image, we noticed large amounts of PII on the network's shared drive.

Memory dump analysis shows potentially malicious processes spaceman.exe and unsecapp.exe on WinServer_3. We are unsure of how these processes were initiated, but will continue to investigate.

Log analysis shows purely IMAP mail traffic travelling between 192.168.100.21 and other hosts. We think that this could be a mail server and will continue to investigate. This type of IMAP log uses an ELK Log Aggregator, which is used primarily on Linux machines. 

### Network Data
1. How many months/weeks/days/hours/minutes worth of network data do you have? **4 days, 7 hours, 45 minutes and 55 seconds**
2. How many packets? **12,334,058**
  - Note: "Killed" exception thrown on 02-27-2020_1.4 that may have affected total packet count.
  - Running `tshark -r 02-27-2020_1.4 | wc` returns 1,565,197 lines/packets
  - Running `countpack()` without `02-27-2020_1.4` returns 10,768,861
  ```
  def countpack():
      counter = 0
      for name in filenames:
          os.system("sudo tshark -r " + name + " > tempfile.txt")
          with open("tempfile.txt") as file:
              for line in file:
                  counter += 1
      print(str(counter))
  ```
3. What times - beginning and ending?
  - Begins: **Feb 28, 2020 05:16:18.989733000 EST**
  - Ends: **Mar 3, 2020 13:02:13.407194000 EST**

### Forensic Image Analysis
1. How many different systems do you have forensic images for? **9**
2. Verify the hashes provided, or provide a hash of the image you received **See table**
3. What are those systems used for? **See table**
4. What user accounts exist on each system? **See table**
5. What other stuff were you provided? **A .zip of ShareDrive_4?**

#### System Info

System        | Purpose                                 | User Accounts                                    
------------- | --------------------------------------- | ------------------------------------------------
IT_2          | Network Analysis and Topologies         | admin, Administrator, DouglasAdams, RoyTremmeman, Guest
Mayor2_2      |                                         | SoniaTheodore, HelenJackson, ShirleyAbdulla, Administratror, admin, Guest
Mayor2_4      |                                         | admin, Administrator, HelenJackson, ShirleyAbdulla, SoniaTheodore, Guest
Police1_1     |                                         | ThomasFord, administrator, admin, Guest, Administrator
Police1_02-28 | Repository of email addresses (13,800+) | ThomasFord, administrator, admin, Guest, Administrator
ShareDrive_1  | Means of sharing office data            | Contains shares using the domain Giacobeville to CommunityDev, giacobeville, InfoTech, MayorsOffice, PlanningAndZoning, Police, and TaxOffice
TaxOffice_1   |                                         |
TaxOffice_2   |                                         |
TaxOffice_4   |                                         | admin, administrator, MikeGold, MillyBond, Guest, Administrator

#### Hash Verification

Images were verified through FTK Imager against the provided hash file(s).

Note: Police1_1 did not have a stored verfication file to run FTK against. TaxOffice_1 hash taken on whole folder.

Image         | Computed SHA1 Hash                       | Verified
------------- | ---------------------------------------- | --------
IT_2          | dfc19952a54e55878b6d7398b57bfe459da0780c | Yes
Mayor2_2      | fdb24e04a874f7c7805acc0dd23f017e12eb32f2 | Yes
Mayor2_4      | dbcc848d19af5af984b9f706c8e9a56599584387 | Yes
Police1_1     | 2075a4d76add4ed77e52e7b377ab13c39e5f2600 | Claims Mismatch
Police1_02-28 | 229eed99e5003cb4fae0927b7af7ec6ea7ea5a5d | Yes
ShareDrive_1  | b4fa5d1466c86d25021843d3c3b383731719ff5d | Yes
TaxOffice_1   | bfde6e0a6132b8e963cbdf2c5725cd621b98ed3f | N/A
TaxOffice_2   | f9f83bc7cf65550d6ef769a2c1f11a9aa7b43c10 | Yes
TaxOffice_4   | 45d06f084c96825df49d5733860044f039595ef3 | Yes

### Memory Forensics
1. Which systems do you have a memory capture for? **See table**
2. What operating systems are each system? **See table**
3. What times/days were the captures completed? **See table**

System      | OS                | Date/Time
----------- | ----------------- | ---------
IT_2        | Win7SP1x64        | 2020-03-01 19:54:10 UTC+0000
Mayor1_3    | Win7SP1x64        | 2020-03-02 21:48:57 UTC+0000
Mayor1_4    | Win7SP1x64        | 2020-03-03 17:58:12 UTC+0000
Mayor2_3    | Win7SP1x64        | 2020-03-02 22:01:10 UTC+0000
Mayor2_4    | Win7SP1x64        | 2020-03-03 17:58:51 UTC+0000
WinServer_1 | Win2016x64_14393  | 2020-02-28 16:50:33 UTC+0000
Winserver_3 | Win2016x64_14393  | 2020-03-02 22:03:27 UTC+0000

### Log Files
1. How many log entries do you have? **89,719**
```
def logcount():
    count = 0
    for file in filenames:
        with open(file) as currentcsv:
            csvreader = csv.reader(currentcsv)
            for line in csvreader:
                count += 1
    print(str(count))
```
2. What are the date/time ranges of the logs?
  - Begins: **2020-02-28 15:06:25.815**
  - Ends: **2020-03-03 13:29:34.351**
3. Describe the types of log entries you have -- what systems generated the log entries? **IMAP Mail Server**
4. Describe the log file aggregator - **ELK Logging is a Linux-based aggregator**
5. Identify any initial findings
  - **GET/SENT for hundreds of UID flags**
  - **Most traffic sourcing from .21?**
  - Source IPs:
192.168.100.21
192.168.100.10
192.168.100.11
192.168.100.14
192.168.100.13
192.168.100.16
192.168.100.18
192.168.100.17

### Indicators of Compromise
  - spaceman.exe and unsecapp.exe on WinServer_3 memory dump
  - Encrypted data on ShareDrive_4

### Questions and Concerns
1. Identify any questions you have for the client
  - Many of the disk images have the standard Administrator account, but they also have admin and administrator, which are manually created accounts. Why?
  - What is the naming scheme? Are Mayor1_3 and Mayor1_4 two different snapshots of the same machine or are they two completely different machines? If the latter, why is there a Mayor2_x?
2. Identify any concerns or issues that your team has
