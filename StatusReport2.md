# Status Report 2
Team 1
  - Brant Goings: **Network, Disk, Memory, BLUF**
  - Sarah Hume: **Logs**
  - Ryan Coe: **Disk**
  - Stephen Giacobe: **BLUF**
  - Parker Chambers: **Disk**
  - Matt Mineo: **Memory**

### Data Description BLUF ###

After analyzing network captures and memory dumps, our team determined that multiple machines either don't exist at all or are on different IP addresses according to the networking charts provided by IT. This may seem like a small matter, but if IT doesn't keep regular track of their network, attackers could infiltrate and add/remove machines at will without anybody else noticing.

_Needs more_

### Network Data ###
- Is your network data contiguous? If not, what does your network data cover? **Yes, the network devices are all found on the 192.168.100.0 subnet. However, the information found within the disk images doesn't seem to line up with the information found in the network captures. See table for more details.**

IP Address      | MAC Address     | Reported Role              | Suspected Role
--------------- | --------------- | -------------------------- | --------------
192.168.100.1   | Dell_8f:09:45   | N/A                        | VMWare Console/Hypervisor
192.168.100.2   | *Unknown*       | Mayor's Office Host        | *IP Address Doesn't Exist*
192.168.100.4   | Dell_a1:82:00   | N/A                        | VMWare Console
192.168.100.5   | Dell_a1:6a:dd   | Police Department Host     | Host
192.168.100.6   | *Unknown*       | Police Department Host     | *IP Address Doesn't Exist*
192.168.100.7   | *Unknown*       | Community Development Host | *IP Address Doesn't Exist*
192.168.100.8   | *Unknown*       | Planning and Zoning Host   | *IP Address Doesn't Exist*
192.168.100.10  | VMware_0b:e9:e1 | IT Host                    | WinServer_1 after Volatility netscan
192.168.100.11  | VMware_38:68:41 | N/A                        | Mayor2_4 and Mayor2_3 after Volatility netscan
192.168.100.12  | VMware_7e:ed:26 | Tax Office Host            | Host
192.168.100.13  | VMware_13:86:e5 | N/A                        | Host
192.168.100.14  | VMware_45:d3:0e | N/A                        | Mayor1_3 and Mayor1_4 after Volatility netscan
192.168.100.15  | *Unknown*       | Mayor's Office Host        | *IP Address Doesn't Exist*
192.168.100.17  | VMware_82:e1:2d | N/A                        | Host
192.168.100.18  | VMware_75:b1:e1 | N/A                        | Host
192.168.100.19  | VMware_0d:c1:c5 | N/A                        | Host
192.168.100.20  | VMware_14:71:4f | N/A                        | Host
192.168.100.21  | VMware_95:d5:c7 | N/A                        | IT_2 after Volatility netscan
192.168.100.180 | VMware_01:bf:ed | N/A                        | Host

- Does your network data cover all systems? If not, identify where in the network that you think the capture covers and what it doesn't cover. **See below diagrams and explanation**

These network diagrams show how the company has grown over the years according to IT_2 user RoyTremmeman. The interesting part is the most recent diagram, 12-10-19, was deleted for an unknown reason.

*6807-Network Diagram 7-20-2015.pdf*
![NetDia072015](./Screenshots/NetDia072015.jpg)

*6805-Network Diagram 4-15-2017.pdf*
![NetDia040517](./Screenshots/NetDia040517.jpg)

*6803-Network Diagram 12-10-2019.pdf*
![NetDi121019](./Screenshots/NetDi121019.jpg)

Below are the most current devices on the network according to IT_2 user RoyTremmeman.

*Network Table.docx*
![NetworkTabledocx](./Screenshots/NetworkTabledocx.jpg)

*Network Table.xlsx*
![NetworkTabledxlsx](./Screenshots/NetworkTablexlsx.jpg)

Based on analysis across Disks, Memory, Network, etc., the network data seems to cover all systems, although the diagrams aren't completely accurate as shown in the first table.

- Do the services that are hosted on the systems make sense for the services that should be offered from those systems. **This is where the network captures differ from the provided network diagrams. See below.**
  - **In the diagrams above, the Domain Controller (DC) is said to be 192.168.100.1, but during analysis we found that to be 192.168.100.10. In addition to the memory dump, port analysis shows 192.168.100.10 had ports 445 and 139 (SMB), 143 (IMAP), 88 (Kerberos), and 389 (LDAP) sourcing from it much more than any other port. These ports are indicative of a Windows Domain Controller running File Sharing on SMB, Mail on IMAP, and Active Directory on Kerberos and LDAP.**
  - **One peculiar machine was 192.168.100.12 (claimed to be the Tax Office host) which had 220 packets sourcing from TCP 80 (HTTP). This isn't very many packets in the long run, but it's worth noting as it's easy to transmit cleartext data over this insecure protocol**
  - **Another instance of similar proportion happened on 192.168.100.19 (an unknown host) but over TCP 443 (HTTPS). This isn't as concerning unless an attacker were to get system-level access, in which case they could transmit malicious encrypted data across the network without being discovered.**

### Forensic Image Analysis ###
- What are those systems used for? **See table**
- What user accounts exist on each system? **See table**
- What do you know about the activities or actions of the user accounts prior to the incident?
- Are there any issues with the accounts that you have found? Are they all authorized? Do you know anything about their passwords? **Local admin hash dumped from memory**
- What software is installed on each system? Was there anything installed recently?
- Identify and explore common vectors of attack - phishing, malicious web pages, malicious software installations, etc.


System        | Purpose                                     | User Accounts                                    
------------- | ------------------------------------------- | ------------------------------------------------
IT_2          | Network Analysis and Topologies             | admin, Administrator, DouglasAdams, RoyTremmeman, Guest
Mayor2_2      |                                             | SoniaTheodore, HelenJackson, ShirleyAbdulla, Administratror, admin, Guest
Mayor2_4      | Contains pdfs on organizational meetings    | admin, Administrator, HelenJackson, ShirleyAbdulla, SoniaTheodore, Guest
Police1_1     |                                             | ThomasFord, administrator, admin, Guest, Administrator
Police1_02-28 | Repository of email addresses (13,800+)     | ThomasFord, administrator, admin, Guest, Administrator
ShareDrive_1  | Means of sharing office data                | Users on domain Giacobeville: CommunityDev, giacobeville, InfoTech, MayorsOffice, PlanningAndZoning, Police, and TaxOffice
TaxOffice_1   | Unable to open .vmdk as of now              | Unable to open .vmdk as of now
TaxOffice_2   |                                             | admin, administrator, MikeGold, MillyBond, Guest, Administrator
TaxOffice_4   | Contains spreadsheets with tax information  | admin, administrator, MikeGold, MillyBond, Guest, Administrator

### Memory Forensics ###
- Is each of the programs running on the system a normal process? 
  - **Most processes running on the systems appear to be normal, with some exceptions (see below)** 
- Are any of the processes running abnormal? 
  - **IT_2, Mayor1_3, Mayor1_4, Mayor2_3, Mayor2_4 all have MRCv120.exe process running on them. It is also seen when performing the Disk Analysis. It is unclear at this point what its function is.** 
  - **All Systems had a higher than expected count of svchost.exe processes running** 
  - **WinServer_3, WinServer_1, Mayor2_4 Systems all have some unexpected output when running psxview**
    - **Multiple processes shown have no name or unexpected names - could potentially be malware trying to hide itself** 
- How much memory does each process take up? Is that a normal amount?
- What do you know about the code that is running?
- Consider spinning up similar systems to do a process-by-process comparison

### Log Files ###
- For each type of log entry - what systems contribute log entries?
	- ELK Logs
		- DC.giacobeville.com
	- DEBUG (not associated with IP addresses)
	- TCPIP (all connect to 192.168.100.10 over SMTP or IMAP)
		- 192.168.100.21
		- 192.168.100.10
		- 192.168.100.11
		- 192.168.100.14
		- 192.168.100.13
		- 192.168.100.16
		- 192.168.100.18
		- 192.168.100.17
	- IMAPD
		- 192.168.100.21
		- 192.168.100.11
		- 192.168.100.14
		- 192.168.100.13
		- 192.168.100.16
		- 192.168.100.18
		- 192.168.100.17
	- SMTPD
		- 192.168.100.10
		- 192.168.100.21
		- 192.168.100.11
		- 192.168.100.14
		- 192.168.100.13
		- 192.168.100.16
		- 192.168.100.18
		- 192.168.100.17
	- APPLICATION
		- Message Senders:
			- RoyTenneman@Giacobeville.com
			- HelenJackson@Giacobeville.com
			- DouglasAdams@giacobeville.com
			- soniatheodore@giacobeville.com
			- RonSwanson@giacobeville.com
			- ThomasFord@giacobeville.com
		- Message Recipients:
			- DavidMcFarlane@Giacobeville.com
			- DouglasAdams@Giacobeville.com
			- HelenJackson@Giacobeville.com
			- MargaretMartinez@giacobeville.com
			- michaelscott@giacobeville.com
			- MikeGold@Giacobeville.com
			- MillyBond@Giacobeville.com
			- RonSwanson@giacobeville.com
			- RoyTenneman@Giacobeville.com
			- ShirleyAbdulla@giacobeville.com
			- soniatheodore@giacobeville.com
			- ThomasFord@giacobeville.com
		
- For each type of log entry - are these loge entries "normal" behavior?
Each of these types of logs are typical of "normal" behavior. High volume of DEBUG logs on 3/2 and 3/3

Types of Log Entries:
DEBUG (2152 logs)
	* 2/28: 299 logs
	* 2/29: 214 logs
	* 3/1: 306 logs
	* 3/2: 968 logs
	* 3/3: 365 logs

TCPIP (263 logs)

	* 2/28 (40 logs)
	  * 192.168.100.21 connected to 192.168.100.10:143
	  * 192.168.100.10 connected to 192.168.100.10:25
	  * 192.168.100.21 connected to 192.168.100.10:587
	  * 192.168.100.11 connected to 192.168.100.10:143
	  * 192.168.100.11 connected to 192.168.100.10:587
	* 2/29 (47 logs)
	  * 192.168.100.21 connected to 192.168.100.10:143
	* 3/1 (58 logs)
	  * 192.168.100.21 connected to 192.168.100.10:143
	  * 192.168.100.11 connected to 192.168.100.10:143
	  * 192.168.100.11 connected to 192.168.100.10:587
	  * 192.168.100.21 connected to 192.168.100.10:587
	* 3/2 (90 logs)
	  * 192.168.100.21 connected to 192.168.100.10:143
	  * 192.168.100.11 connected to 192.168.100.10:143
	  * 192.168.100.11 connected to 192.168.100.10:587
	  * 192.168.100.14 connected to 192.168.100.10:143
	  * 192.168.100.14 connected to 192.168.100.10:587
	  * 192.168.100.21 connected to 192.168.100.10:587
	  * 192.168.100.13 connected to 192.168.100.10:143
	  * 192.168.100.13 connected to 192.168.100.10:587
	  * 192.168.100.16 connected to 192.168.100.10:143
	  * 192.168.100.16 connected to 192.168.100.10:587
	  * 192.168.100.18 connected to 192.168.100.10:143
	  * 192.168.100.17 connected to 192.168.100.10:143
	* 3/3 (28 logs)
	  * 192.168.100.21 connected to 192.168.100.10:143
	  * 192.168.100.14 connected to 192.168.100.10:143
	  * 192.168.100.14 connected to 192.168.100.10:587
	  * 192.168.100.11 connected to 192.168.100.10:143
	  * 192.168.100.11 connected to 192.168.100.10:587
	  * 192.168.100.21 connected to 192.168.100.10:587
	  * DNS - Query failure. Treating as temporary failure. Query: 21.100.168.192.in-addr.arpa, Type: 12, DnsQuery return value: 1460.
  
IMAPD (86593 logs)
	* 2/28 (14652 logs)
	  * 192.168.100.21
	  * 192.168.100.11
	* 2/29 (1911 logs)
	  * 192.168.100.21
	* 3/1 (11734 logs)
	  *  192.168.100.21
	  *  192.168.100.11
	* 3/2 (40422 logs)
	  * 192.168.100.11
	  * 192.168.100.21
	  * 192.168.100.14
	  * 192.168.100.13
	  * 192.168.100.16
	  * 192.168.100.18
	  * 192.168.100.17'
	* 3/3 (17874 logs)
	  * 192.168.100.21
	  * 192.168.100.14
	  * 192.168.100.11
  
SMTPD (641 logs)
	* 2/28 (107 logs)
	  * 192.168.100.10
	  * 192.168.100.21
	  * 192.168.100.11
	* 2/29 (0 logs)
	* 3/1 (56 logs)
	  * 192.168.100.11
	  * 192.168.100.21
	* 3/2 (360 logs)
	  * 192.168.100.11
	  * 192.168.100.14
	  * 192.168.100.21
	  * 192.168.100.13
	  * 192.168.100.16
	  * 192.168.100.18
	  * 192.168.100.17
	* 3/3 (118 logs)
	  * 192.168.100.14
	  * 192.168.100.11
	  * 192.168.100.21
  
APPLICATION (70 logs)
	* 2/28 (12 logs)
	  *	Delivering message from RoyTenneman@Giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{0315560A-9E33-4FA1-962F-05002DF6E83F}.eml"
		*	Delivering message from HelenJackson@Giacobeville.com to RoyTenneman@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{F05ED0B6-CA1D-415E-B38A-AD89BF39A105}.eml"
		*	Delivering message from HelenJackson@Giacobeville.com to DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{D8ED431A-7258-4A86-AA06-2A4487488DEA}.eml"
		*	Delivering message from DouglasAdams@giacobeville.com to MikeGold@Giacobeville.com, ShirleyAbdulla@giacobeville.com, HelenJackson@Giacobeville.com, ThomasFord@giacobeville.com, RonSwanson@giacobeville.com, DavidMcFarlane@Giacobeville.com, MargaretMartinez@giacobeville.com, MillyBond@Giacobeville.com, michaelscott@giacobeville.com, soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{545E15C9-FBDF-40F3-8F79-7F2F2CDA4F4D}.eml"
		*	Delivering message from HelenJackson@Giacobeville.com to soniatheodore@giacobeville.com, RoyTenneman@Giacobeville.com, DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{2A2E7C63-8FEF-49B9-93D0-9E2B042F27F1}.eml"
		*	Delivering message from DouglasAdams@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{1E9FC561-9CC6-45F3-860E-41EDCB6D5080}.eml"
	* 2/29 (0 logs)
	* 3/1 (8 logs)
	  * Delivering message from HelenJackson@Giacobeville.com to DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{0C54C1D3-4C9F-4BC6-85B5-AD9BCABEA75D}.eml"
	  * Delivering message from DouglasAdams@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{817D9224-9391-4027-B03C-B1A48705A732}.eml"
	  * Delivering message from DouglasAdams@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{370BC505-9DB3-4551-9E60-115DB949970F}.eml"
	  * Delivering message from HelenJackson@Giacobeville.com to DouglasAdams@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{11D80F1A-4B2B-46C5-A693-082D247F78A0}.eml"
	* 3/2 (34 logs)
	  * Delivering message from HelenJackson@Giacobeville.com to RoyTenneman@Giacobeville.com, DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{1ABF516D-DAC0-4477-9922-642310B7F716}.eml"
	  * Delivering message from soniatheodore@giacobeville.com to RoyTenneman@Giacobeville.com, douglasadams@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{1FA9391C-5493-4A97-9E4C-0A1AEDC341CF}.eml"
	  * Delivering message from DouglasAdams@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{5655BF4E-0637-4788-AA0D-9BCEB57980A3}.eml"
	  * Delivering message from DouglasAdams@giacobeville.com to soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{8ECBE3AA-3F05-4986-9FF4-366396AE77DF}.eml"
	  * Delivering message from HelenJackson@Giacobeville.com to DouglasAdams@Giacobeville.com, RoyTenneman@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{F8AB9851-36B7-436B-932E-D913569FAB90}.eml"
	  * Delivering message from DouglasAdams@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{9C62BE21-4FC8-40CC-8252-1876DBBF981F}.eml"
	  * Delivering message from HelenJackson@Giacobeville.com to RoyTenneman@Giacobeville.com, DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{B718356D-021D-40A8-9744-C60FE497991F}.eml"
	  * Delivering message from RonSwanson@giacobeville.com to DouglasAdams@Giacobeville.com, RoyTenneman@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{72947CD9-BC30-4A00-A79D-5402CF46F6E6}.eml"
	  * Delivering message from RoyTenneman@Giacobeville.com to ThomasFord@Giacobeville.com, SoniaTheodore@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, RonSwanson@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, HelenJackson@Giacobeville.com, DavidMcFarlane@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{27475E00-7105-49E3-9A69-473071CDA3E6}.eml"
	  * Delivering message from soniatheodore@giacobeville.com to ThomasFord@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, RonSwanson@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, HelenJackson@Giacobeville.com, DavidMcFarlane@Giacobeville.com, RoyTenneman@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{346904F9-9C05-467E-A64F-CF6817A415CA}.eml"
	  * Delivering message from RoyTenneman@Giacobeville.com to soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{AE3C631C-AA1B-4448-BDD5-42589354E037}.eml"
	  * Delivering message from RonSwanson@giacobeville.com to ThomasFord@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, HelenJackson@Giacobeville.com, DavidMcFarlane@Giacobeville.com, RoyTenneman@Giacobeville.com, soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{8102E9C2-1528-4198-91CC-C82382E2BEB9}.eml"
	  * Delivering message from RonSwanson@giacobeville.com to ThomasFord@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, HelenJackson@Giacobeville.com, DavidMcFarlane@Giacobeville.com, RoyTenneman@Giacobeville.com, soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{DF2F5F1A-673A-431B-978B-39D6B9B0CFD0}.eml"
	  * Delivering message from HelenJackson@Giacobeville.com to ThomasFord@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, DavidMcFarlane@Giacobeville.com, RoyTenneman@Giacobeville.com, soniatheodore@giacobeville.com, RonSwanson@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{4344C0DF-FC43-4C3D-863D-4F7F51BF15A6}.eml"
	  * Delivering message from ThomasFord@giacobeville.com to ShirleyAbdulla@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, DavidMcFarlane@Giacobeville.com, RoyTenneman@Giacobeville.com, soniatheodore@giacobeville.com, RonSwanson@giacobeville.com, HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{A82D5E93-1DA8-499C-B50D-C017AD1A23D5}.eml"
	  * Delivering message from soniatheodore@giacobeville.com to ShirleyAbdulla@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, DavidMcFarlane@Giacobeville.com, RoyTenneman@Giacobeville.com, RonSwanson@giacobeville.com, HelenJackson@Giacobeville.com, ThomasFord@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{F42F7B72-D4EE-45C1-9D7C-C3D79D2C13C6}.eml"

	 * 3/3 (16 logs)
	  * "Starting servers..."
	  * "Servers started."
	  *  Delivering message from soniatheodore@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{348C588D-644C-4E00-A5E2-BD71802C0C83}.eml"
	  *  Delivering message from HelenJackson@Giacobeville.com to soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{31EC0802-8EFB-45AB-BE53-0C011D967497}.eml"
	  *  Delivering message from HelenJackson@Giacobeville.com to RoyTenneman@Giacobeville.com, DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{3DB2BEC5-D7E7-43DF-98FF-4DDBC0E9ED64}.eml"
	  *  Delivering message from RoyTenneman@Giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{F2B0A721-8196-451E-940C-B7EEF17BE3BB}.eml"
	  *  Delivering message from HelenJackson@Giacobeville.com to soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{EA85ECFE-7D8E-4F64-9EA2-ED5D1F69423A}.eml"
	  *  Delivering message from soniatheodore@giacobeville.com to MikeGold@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{CF8D9C1E-9D5C-4EE1-8262-C72F33AD95D4}.eml"
	  *  Delivering message from RoyTenneman@Giacobeville.com to ThomasFord@Giacobeville.com, SoniaTheodore@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, RonSwanson@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, HelenJackson@Giacobeville.com, DavidMcFarlane@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{EEB88A0D-A27C-4A9B-9384-E7D1933DE9CE}.eml"


- Are there any time gaps in your log files?
* There is a time gap on 2020-03-02 between 2020-03-02 13:23:33.345 and 16:32:24.835.
* There is another time gap on 2020-03-02 from 17:53:01.094 to 00:00:00.00.
* On 2020-03-03, logs are only captured between 12:10:01.493 and 13:29:34.351.
- Are there any unusual log entries? If so, what makes them unusual?
* There are "Server started" APPLICATION logs on 3/3 midday but not on any of the other days. I would think if this did occur, it would be early morning
* There were DNS query failure TCPIP logs on 3/3 but not any of the other days.
* The same few email users are sending all of the emails.


### IOCs ###
- Identify any preliminary IOCs that you have found.  Provide some statement of confidence of your analysis of those IOCs.
  - Large numbers of cat pictures found on ShareDrive paired with their "cleartext" partner. This indicates some type of ransomware attack.

### Questions and Concerns ###
- Identify any questions you have for the client
- Identify any concerns or issues that your team has
