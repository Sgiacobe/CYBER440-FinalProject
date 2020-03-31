# Log Analysis

How many log entries do you have? 89,719
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

What are the date/time ranges of the logs?
- Begins: 2020-02-28 15:06:25.815
- Ends: 2020-03-03 13:29:34.351

Describe the types of log entries you have -- what systems generated the log entries? IMAP Mail Server

Describe the log file aggregator - ELK Logging is a Linux-based aggregator

Identify any initial findings
- GET/SENT for hundreds of UID flags
- Most traffic sourcing from .21
- Source IPs: 192.168.100.21 192.168.100.10 192.168.100.11 192.168.100.14 192.168.100.13 192.168.100.16 192.168.100.18 192.168.100.17

**Mail Domain:** giacobeville.com

**Users:**
* DavidMcFarlane@Giacobeville.com
* DouglasAdams@giacobeville.com
* HelenJackson@Giacobeville.com
* MargaretMartinez@giacobeville.com
* michaelscott@giacobeville.com
* MikeGold@Giacobeville.com
* MillyBond@Giacobeville.com
* RonSwanson@giacobeville.com
* RoyTenneman@Giacobeville.com
* ShirleyAbdulla@giacobeville.com
* soniatheodore@giacobeville.com
* ThomasFord@giacobeville.com

## Elk Logs ##

## hmailserver_2020-02-28.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.10
* 192.168.100.11

**Users:**
* DavidMcFarlane@Giacobeville.com
* DouglasAdams@giacobeville.com
* HelenJackson@Giacobeville.com
* MargaretMartinez@giacobeville.com
* michaelscott@giacobeville.com
* MikeGold@Giacobeville.com
* MillyBond@Giacobeville.com
* RonSwanson@giacobeville.com
* RoyTenneman@Giacobeville.com
* ShirleyAbdulla@giacobeville.com
* soniatheodore@giacobeville.com
* ThomasFord@giacobeville.com

**Logins:**
* "IMAPD"	5436	2	"2020-02-28 15:06:25.909"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5440	6	"2020-02-28 15:06:26.081"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5436	2	"2020-02-28 15:06:26.123"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	6	"2020-02-28 15:06:26.136"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	7	"2020-02-28 15:06:30.000"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5440	7	"2020-02-28 15:06:30.037"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	8	"2020-02-28 15:06:40.584"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5432	8	"2020-02-28 15:06:40.614"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5428	10	"2020-02-28 15:06:42.472"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5428	10	"2020-02-28 15:06:42.499"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5444	4	"2020-02-28 15:08:26.413"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5444	11	"2020-02-28 15:08:39.717"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5444	11	"2020-02-28 15:08:39.750"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	13	"2020-02-28 15:21:55.825"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	13	"2020-02-28 15:21:55.871"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	14	"2020-02-28 15:22:20.259"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5436	14	"2020-02-28 15:22:20.291"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	15	"2020-02-28 15:22:20.605"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5440	15	"2020-02-28 15:22:20.639"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	16	"2020-02-28 15:22:32.956"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	16	"2020-02-28 15:22:32.986"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5424	17	"2020-02-28 15:22:34.385"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5424	17	"2020-02-28 15:22:34.414"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5428	12	"2020-02-28 15:22:41.887"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5444	18	"2020-02-28 15:23:05.938"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	18	"2020-02-28 15:23:05.971"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	20	"2020-02-28 15:28:11.866"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	20	"2020-02-28 15:28:11.911"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5416	19	"2020-02-28 15:31:40.756"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5440	21	"2020-02-28 15:32:07.584"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5440	21	"2020-02-28 15:32:07.613"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5440	22	"2020-02-28 15:35:52.345"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5440	23	"2020-02-28 15:36:05.213"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	23	"2020-02-28 15:36:05.269"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	25	"2020-02-28 15:36:08.095"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	25	"2020-02-28 15:36:08.138"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5420	24	"2020-02-28 15:41:21.511"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "SMTPD"	5436	27	"2020-02-28 15:42:23.165"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5416	29	"2020-02-28 16:20:35.047"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	29	"2020-02-28 16:20:35.088"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	30	"2020-02-28 16:50:35.713"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	30	"2020-02-28 16:50:35.757"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	31	"2020-02-28 17:20:37.554"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	31	"2020-02-28 17:20:37.613"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	32	"2020-02-28 17:50:37.693"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	32	"2020-02-28 17:50:37.733"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	33	"2020-02-28 18:20:37.525"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	33	"2020-02-28 18:20:37.564"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	34	"2020-02-28 18:50:38.007"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	34	"2020-02-28 18:50:38.047"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	35	"2020-02-28 19:20:38.094"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	35	"2020-02-28 19:20:38.145"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	36	"2020-02-28 19:50:38.491"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	36	"2020-02-28 19:50:38.530"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	37	"2020-02-28 20:20:39.520"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	37	"2020-02-28 20:20:39.559"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	38	"2020-02-28 20:50:40.999"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	38	"2020-02-28 20:50:41.034"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	39	"2020-02-28 21:20:40.319"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	39	"2020-02-28 21:20:40.361"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	40	"2020-02-28 21:50:40.984"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	40	"2020-02-28 21:50:41.024"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	41	"2020-02-28 22:20:41.401"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	41	"2020-02-28 22:20:41.440"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	42	"2020-02-28 22:50:42.057"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	42	"2020-02-28 22:50:42.094"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	43	"2020-02-28 23:20:42.225"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	43	"2020-02-28 23:20:42.271"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	44	"2020-02-28 23:50:44.147"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	44	"2020-02-28 23:50:44.186"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"

## hmailserver_2020-02-29.log ##
**Source IPs:**
* 192.168.100.21

**Users:**
* DouglasAdams@giacobeville.com

**Logins**
* "IMAPD"	5416	45	"2020-02-29 00:20:43.118"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	45	"2020-02-29 00:20:43.157"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	46	"2020-02-29 00:50:44.268"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	46	"2020-02-29 00:50:44.305"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	47	"2020-02-29 01:20:43.885"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	47	"2020-02-29 01:20:43.919"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	48	"2020-02-29 02:00:44.468"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	48	"2020-02-29 02:00:44.509"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	49	"2020-02-29 02:30:46.315"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	49	"2020-02-29 02:30:46.353"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	50	"2020-02-29 03:00:46.645"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	50	"2020-02-29 03:00:46.713"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	51	"2020-02-29 03:30:47.159"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	51	"2020-02-29 03:30:47.199"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	52	"2020-02-29 04:00:47.393"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	52	"2020-02-29 04:00:47.447"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	53	"2020-02-29 04:30:48.278"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	53	"2020-02-29 04:30:48.315"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	54	"2020-02-29 05:00:50.229"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	54	"2020-02-29 05:00:50.272"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	55	"2020-02-29 05:30:50.307"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	55	"2020-02-29 05:30:50.345"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	56	"2020-02-29 06:00:49.426"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	56	"2020-02-29 06:00:49.473"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	57	"2020-02-29 06:30:49.917"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	57	"2020-02-29 06:30:49.974"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	58	"2020-02-29 07:00:50.294"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	58	"2020-02-29 07:00:50.333"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	59	"2020-02-29 07:30:50.670"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	59	"2020-02-29 07:30:50.704"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	60	"2020-02-29 08:00:50.843"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	60	"2020-02-29 08:00:50.881"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	61	"2020-02-29 08:30:52.810"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	61	"2020-02-29 08:30:52.867"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	62	"2020-02-29 09:00:52.687"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	62	"2020-02-29 09:00:52.724"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	63	"2020-02-29 09:30:53.322"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	63	"2020-02-29 09:30:53.360"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	64	"2020-02-29 10:00:52.624"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	64	"2020-02-29 10:00:52.659"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	65	"2020-02-29 10:30:52.943"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	65	"2020-02-29 10:30:52.984"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	66	"2020-02-29 11:00:54.013"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	66	"2020-02-29 11:00:54.048"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	67	"2020-02-29 11:30:55.163"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	67	"2020-02-29 11:30:55.203"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	68	"2020-02-29 12:00:55.635"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	68	"2020-02-29 12:00:55.671"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	69	"2020-02-29 12:30:55.571"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	69	"2020-02-29 12:30:55.610"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	70	"2020-02-29 13:00:56.042"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	70	"2020-02-29 13:00:56.082"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	71	"2020-02-29 13:30:56.384"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	71	"2020-02-29 13:30:56.420"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	72	"2020-02-29 14:01:08.707"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	72	"2020-02-29 14:01:08.749"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	73	"2020-02-29 14:41:10.218"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	73	"2020-02-29 14:41:10.254"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	74	"2020-02-29 15:11:10.277"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	74	"2020-02-29 15:11:10.355"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	75	"2020-02-29 15:41:09.249"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	75	"2020-02-29 15:41:09.285"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	76	"2020-02-29 16:11:09.534"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	76	"2020-02-29 16:11:09.608"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	77	"2020-02-29 16:41:11.441"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	77	"2020-02-29 16:41:11.477"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	78	"2020-02-29 17:11:11.602"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	78	"2020-02-29 17:11:11.658"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	79	"2020-02-29 17:41:11.486"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	79	"2020-02-29 17:41:11.537"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	80	"2020-02-29 18:11:13.018"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	80	"2020-02-29 18:11:13.056"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	81	"2020-02-29 18:41:13.502"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	81	"2020-02-29 18:41:13.542"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	82	"2020-02-29 19:11:13.762"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	82	"2020-02-29 19:11:13.806"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	83	"2020-02-29 19:41:13.499"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	83	"2020-02-29 19:41:13.535"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	84	"2020-02-29 20:11:14.328"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	84	"2020-02-29 20:11:14.366"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	85	"2020-02-29 20:41:14.461"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	85	"2020-02-29 20:41:14.501"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	86	"2020-02-29 21:11:13.988"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	86	"2020-02-29 21:11:14.040"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	87	"2020-02-29 21:41:14.532"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	87	"2020-02-29 21:41:14.567"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	88	"2020-02-29 22:11:15.118"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	88	"2020-02-29 22:11:15.155"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	89	"2020-02-29 22:41:16.766"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	89	"2020-02-29 22:41:16.804"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	90	"2020-02-29 23:11:17.011"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	90	"2020-02-29 23:11:17.062"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	91	"2020-02-29 23:41:17.049"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	91	"2020-02-29 23:41:17.089"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"

## hmailserver_2020-03-01.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.11

**Users:**
* DouglasAdams@giacobeville.com
* HelenJackson@Giacobeville.com

**Logins**
* "IMAPD"	5416	92	"2020-03-01 00:11:17.370"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	92	"2020-03-01 00:11:17.408"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	93	"2020-03-01 00:41:17.190"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	93	"2020-03-01 00:41:17.229"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	94	"2020-03-01 01:11:17.492"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	94	"2020-03-01 01:11:17.531"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	95	"2020-03-01 01:41:19.538"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	95	"2020-03-01 01:41:19.575"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	96	"2020-03-01 02:11:18.317"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	96	"2020-03-01 02:11:18.358"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	97	"2020-03-01 02:41:19.935"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	97	"2020-03-01 02:41:19.971"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	98	"2020-03-01 03:11:20.035"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	98	"2020-03-01 03:11:20.103"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	99	"2020-03-01 03:41:20.485"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	99	"2020-03-01 03:41:20.524"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	100	"2020-03-01 04:11:21.092"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	100	"2020-03-01 04:11:21.154"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	101	"2020-03-01 04:41:22.968"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	101	"2020-03-01 04:41:23.003"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	102	"2020-03-01 05:11:33.122"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	102	"2020-03-01 05:11:33.175"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	103	"2020-03-01 05:51:33.625"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	103	"2020-03-01 05:51:33.674"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	104	"2020-03-01 06:21:34.876"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	104	"2020-03-01 06:21:34.927"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	105	"2020-03-01 06:51:34.284"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	105	"2020-03-01 06:51:34.321"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	106	"2020-03-01 07:21:35.259"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	106	"2020-03-01 07:21:35.297"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	107	"2020-03-01 07:51:35.500"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	107	"2020-03-01 07:51:35.537"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	108	"2020-03-01 08:21:35.697"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	108	"2020-03-01 08:21:35.739"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	109	"2020-03-01 08:51:35.434"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	109	"2020-03-01 08:51:35.487"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	110	"2020-03-01 09:21:35.786"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	110	"2020-03-01 09:21:35.832"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	111	"2020-03-01 09:51:36.106"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	111	"2020-03-01 09:51:36.151"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	112	"2020-03-01 10:21:37.602"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	112	"2020-03-01 10:21:37.643"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	113	"2020-03-01 10:51:38.160"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	113	"2020-03-01 10:51:38.195"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	114	"2020-03-01 11:21:38.156"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	114	"2020-03-01 11:21:38.190"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	115	"2020-03-01 11:51:38.535"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	115	"2020-03-01 11:51:38.569"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	116	"2020-03-01 12:21:37.734"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	116	"2020-03-01 12:21:37.770"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	117	"2020-03-01 12:51:38.285"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	117	"2020-03-01 12:51:38.328"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	118	"2020-03-01 13:21:38.546"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5444	118	"2020-03-01 13:21:38.581"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	119	"2020-03-01 13:31:36.327"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	119	"2020-03-01 13:31:36.361"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	120	"2020-03-01 13:32:11.203"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	120	"2020-03-01 13:32:11.231"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	121	"2020-03-01 13:32:11.316"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	121	"2020-03-01 13:32:11.343"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	122	"2020-03-01 13:32:22.092"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5444	122	"2020-03-01 13:32:22.117"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	123	"2020-03-01 13:32:22.982"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5440	123	"2020-03-01 13:32:23.009"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5432	28	"2020-03-01 13:48:20.558"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5416	124	"2020-03-01 13:48:43.605"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5416	124	"2020-03-01 13:48:43.630"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5436	125	"2020-03-01 14:06:05.102"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5428	126	"2020-03-01 14:06:16.811"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5428	126	"2020-03-01 14:06:16.842"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	128	"2020-03-01 14:06:37.964"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	128	"2020-03-01 14:06:37.999"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5428	129	"2020-03-01 14:32:31.247"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5428	129	"2020-03-01 14:32:31.282"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5440	127	"2020-03-01 14:36:50.724"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5436	130	"2020-03-01 14:37:02.270"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	130	"2020-03-01 14:37:02.310"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5444	131	"2020-03-01 14:40:38.705"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5420	132	"2020-03-01 14:41:50.963"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5420	132	"2020-03-01 14:41:50.999"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	134	"2020-03-01 14:43:24.473"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	134	"2020-03-01 14:43:24.508"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	135	"2020-03-01 16:41:38.896"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	135	"2020-03-01 16:41:38.950"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	136	"2020-03-01 17:11:40.177"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	136	"2020-03-01 17:11:40.227"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	137	"2020-03-01 17:41:41.202"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	137	"2020-03-01 17:41:41.253"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	138	"2020-03-01 18:11:40.650"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	138	"2020-03-01 18:11:40.686"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	139	"2020-03-01 18:41:40.598"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	139	"2020-03-01 18:41:40.683"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	140	"2020-03-01 19:11:41.636"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	140	"2020-03-01 19:11:41.694"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	141	"2020-03-01 19:41:41.556"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	141	"2020-03-01 19:41:41.610"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	142	"2020-03-01 20:11:42.118"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	142	"2020-03-01 20:11:42.201"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	143	"2020-03-01 20:41:44.180"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	143	"2020-03-01 20:41:44.240"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	144	"2020-03-01 21:11:43.662"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	144	"2020-03-01 21:11:43.741"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	145	"2020-03-01 21:41:43.848"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	145	"2020-03-01 21:41:43.940"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	146	"2020-03-01 22:11:44.179"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	146	"2020-03-01 22:11:44.277"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	147	"2020-03-01 22:41:44.254"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	147	"2020-03-01 22:41:44.310"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	148	"2020-03-01 23:11:43.948"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	148	"2020-03-01 23:11:44.021"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	149	"2020-03-01 23:41:44.613"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	149	"2020-03-01 23:41:44.693"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"

## hmailserver_2020-03-02.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.11
* 192.168.100.14
* 192.168.100.13
* 192.168.100.16
* 192.168.100.18
* 192.168.100.17

**Users**
* DouglasAdams@giacobeville.com
* HelenJackson@Giacobeville.com
* soniatheodore@giacobeville.com
* RonSwanson@giacobeville.com
* RoyTenneman@Giacobeville.com
* ThomasFord@giacobeville.com
* MillyBond@Giacobeville.com
* MargaretMartinez@giacobeville.com

**Logins:**
* "IMAPD"	5432	150	"2020-03-02 00:11:45.121"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	150	"2020-03-02 00:11:45.182"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	151	"2020-03-02 00:41:46.590"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	151	"2020-03-02 00:41:46.652"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	152	"2020-03-02 01:11:46.848"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	152	"2020-03-02 01:11:46.926"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	153	"2020-03-02 01:41:45.581"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	153	"2020-03-02 01:41:45.656"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	154	"2020-03-02 02:11:46.513"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	154	"2020-03-02 02:11:46.582"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	155	"2020-03-02 02:41:47.289"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	155	"2020-03-02 02:41:47.355"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	156	"2020-03-02 03:11:47.285"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	156	"2020-03-02 03:11:47.353"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	157	"2020-03-02 03:41:47.385"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	157	"2020-03-02 03:41:47.437"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	158	"2020-03-02 04:11:47.626"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	158	"2020-03-02 04:11:47.661"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	159	"2020-03-02 04:41:47.941"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	159	"2020-03-02 04:41:47.994"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	160	"2020-03-02 05:11:57.345"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	160	"2020-03-02 05:11:57.378"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	161	"2020-03-02 05:51:58.983"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	161	"2020-03-02 05:51:59.028"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	162	"2020-03-02 06:21:58.988"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	162	"2020-03-02 06:21:59.020"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	163	"2020-03-02 06:51:58.826"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	163	"2020-03-02 06:51:58.863"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	164	"2020-03-02 07:21:59.076"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5412	164	"2020-03-02 07:21:59.116"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	165	"2020-03-02 07:52:00.117"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	165	"2020-03-02 07:52:00.153"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	166	"2020-03-02 08:22:00.061"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	166	"2020-03-02 08:22:00.115"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	167	"2020-03-02 08:52:00.019"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	167	"2020-03-02 08:52:00.070"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	168	"2020-03-02 09:22:01.953"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	168	"2020-03-02 09:22:02.030"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	169	"2020-03-02 09:52:02.297"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5432	169	"2020-03-02 09:52:02.350"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	170	"2020-03-02 10:22:02.135"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	170	"2020-03-02 10:22:02.176"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	171	"2020-03-02 10:31:34.424"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5440	171	"2020-03-02 10:31:34.461"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	172	"2020-03-02 10:52:02.460"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	172	"2020-03-02 10:52:02.503"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	173	"2020-03-02 11:22:04.578"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	173	"2020-03-02 11:22:04.625"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	174	"2020-03-02 11:52:04.852"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	174	"2020-03-02 11:52:04.915"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	175	"2020-03-02 12:22:05.236"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	175	"2020-03-02 12:22:05.289"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	176	"2020-03-02 12:52:04.845"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	176	"2020-03-02 12:52:04.880"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	177	"2020-03-02 16:32:26.437"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5420	177	"2020-03-02 16:32:26.493"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	178	"2020-03-02 16:34:22.782"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5420	178	"2020-03-02 16:34:22.818"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	179	"2020-03-02 16:34:22.946"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5420	179	"2020-03-02 16:34:22.978"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5412	180	"2020-03-02 16:34:36.468"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5412	180	"2020-03-02 16:34:36.509"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	181	"2020-03-02 16:34:37.831"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5436	181	"2020-03-02 16:34:37.865"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5412	133	"2020-03-02 16:40:16.094"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5416	182	"2020-03-02 16:40:56.625"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5416	182	"2020-03-02 16:40:56.658"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	184	"2020-03-02 16:41:25.468"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	184	"2020-03-02 16:41:25.508"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	185	"2020-03-02 16:41:45.909"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5444	185	"2020-03-02 16:41:45.951"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	186	"2020-03-02 16:41:51.150"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5436	186	"2020-03-02 16:41:51.188"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	187	"2020-03-02 16:41:56.803"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5436	187	"2020-03-02 16:41:56.835"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	188	"2020-03-02 16:41:57.544"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5436	188	"2020-03-02 16:41:57.576"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	189	"2020-03-02 16:42:17.075"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5440	189	"2020-03-02 16:42:17.110"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	190	"2020-03-02 16:42:38.469"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5440	190	"2020-03-02 16:42:38.505"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5436	183	"2020-03-02 16:42:39.044"	"192.168.100.14"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "SMTPD"	5416	192	"2020-03-02 16:42:45.252"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5416	191	"2020-03-02 16:42:52.296"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5416	191	"2020-03-02 16:42:52.342"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5416	194	"2020-03-02 16:43:12.959"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5416	194	"2020-03-02 16:43:12.993"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5424	193	"2020-03-02 16:44:18.153"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5440	195	"2020-03-02 16:44:39.605"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5440	195	"2020-03-02 16:44:39.637"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5416	196	"2020-03-02 16:57:56.315"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "SMTPD"	5440	198	"2020-03-02 16:59:41.952"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5420	197	"2020-03-02 16:59:58.466"	"192.168.100.21"	"RECEIVED: 3 login "DouglasAdams@giacobeville.com" ***"
* "IMAPD"	5420	197	"2020-03-02 16:59:58.513"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5440	199	"2020-03-02 17:00:18.299"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5440	200	"2020-03-02 17:00:33.531"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5440	200	"2020-03-02 17:00:33.593"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5420	201	"2020-03-02 17:02:29.042"	"192.168.100.13"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5412	202	"2020-03-02 17:02:41.014"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5412	202	"2020-03-02 17:02:41.061"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	204	"2020-03-02 17:02:53.762"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5420	204	"2020-03-02 17:02:53.835"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5436	205	"2020-03-02 17:02:55.553"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5436	205	"2020-03-02 17:02:55.616"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	206	"2020-03-02 17:02:57.238"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5420	206	"2020-03-02 17:02:57.282"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	207	"2020-03-02 17:02:59.778"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5420	207	"2020-03-02 17:02:59.824"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	208	"2020-03-02 17:13:43.167"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5420	208	"2020-03-02 17:13:43.234"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	209	"2020-03-02 17:14:01.329"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5420	209	"2020-03-02 17:14:01.376"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	210	"2020-03-02 17:14:01.663"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5420	210	"2020-03-02 17:14:01.712"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5444	211	"2020-03-02 17:14:25.747"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5444	211	"2020-03-02 17:14:25.826"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5428	212	"2020-03-02 17:14:28.572"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5428	212	"2020-03-02 17:14:28.602"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5412	203	"2020-03-02 17:15:58.567"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "SMTPD"	5440	214	"2020-03-02 17:16:51.658"	"192.168.100.14"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5428	213	"2020-03-02 17:17:04.375"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5428	213	"2020-03-02 17:17:04.499"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5420	216	"2020-03-02 17:17:07.828"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5420	216	"2020-03-02 17:17:07.864"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	217	"2020-03-02 17:19:53.055"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5432	217	"2020-03-02 17:19:53.106"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5420	215	"2020-03-02 17:21:42.255"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5436	218	"2020-03-02 17:22:00.716"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5436	218	"2020-03-02 17:22:00.780"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5440	219	"2020-03-02 17:31:05.427"	"192.168.100.13"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5432	220	"2020-03-02 17:31:21.182"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5432	220	"2020-03-02 17:31:21.337"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5444	221	"2020-03-02 17:32:23.854"	"192.168.100.13"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5436	222	"2020-03-02 17:33:29.207"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5436	222	"2020-03-02 17:33:29.309"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5428	224	"2020-03-02 17:33:48.370"	"192.168.100.13"	"RECEIVED: 3 login "RonSwanson@giacobeville.com" ***"
* "IMAPD"	5428	224	"2020-03-02 17:33:48.496"	"192.168.100.13"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5428	223	"2020-03-02 17:34:16.962"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5424	225	"2020-03-02 17:34:32.461"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5424	225	"2020-03-02 17:34:32.558"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	227	"2020-03-02 17:42:47.101"	"192.168.100.16"	"RECEIVED: 3 login "ThomasFord@giacobeville.com" ***"
* "IMAPD"	5440	227	"2020-03-02 17:42:47.167"	"192.168.100.16"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5404	228	"2020-03-02 17:43:14.600"	"192.168.100.16"	"RECEIVED: 3 login "ThomasFord@giacobeville.com" ***"
* "IMAPD"	5404	228	"2020-03-02 17:43:14.639"	"192.168.100.16"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5404	229	"2020-03-02 17:43:15.094"	"192.168.100.16"	"RECEIVED: 3 login "ThomasFord@giacobeville.com" ***"
* "IMAPD"	5404	229	"2020-03-02 17:43:15.137"	"192.168.100.16"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5408	230	"2020-03-02 17:43:30.338"	"192.168.100.16"	"RECEIVED: 3 login "ThomasFord@giacobeville.com" ***"
* "IMAPD"	5408	230	"2020-03-02 17:43:30.417"	"192.168.100.16"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5424	226	"2020-03-02 17:44:08.943"	"192.168.100.16"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5424	231	"2020-03-02 17:44:58.342"	"192.168.100.16"	"RECEIVED: 3 login "ThomasFord@giacobeville.com" ***"
* "IMAPD"	5424	231	"2020-03-02 17:44:58.401"	"192.168.100.16"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5440	233	"2020-03-02 17:45:00.478"	"192.168.100.16"	"RECEIVED: 3 login "ThomasFord@giacobeville.com" ***"
* "IMAPD"	5440	233	"2020-03-02 17:45:00.545"	"192.168.100.16"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5420	232	"2020-03-02 17:46:02.238"	"192.168.100.14"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5408	234	"2020-03-02 17:46:17.424"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5408	234	"2020-03-02 17:46:17.513"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5400	236	"2020-03-02 17:46:31.166"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5400	236	"2020-03-02 17:46:31.282"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5404	238	"2020-03-02 17:46:50.732"	"192.168.100.18"	"RECEIVED: 3 login "MillyBond@Giacobeville.com" ***"
* "IMAPD"	5404	238	"2020-03-02 17:46:50.791"	"192.168.100.18"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5432	239	"2020-03-02 17:47:33.225"	"192.168.100.17"	"RECEIVED: 3 login "MargaretMartinez@giacobeville.com" ***"
* "IMAPD"	5432	239	"2020-03-02 17:47:33.271"	"192.168.100.17"	"SENT: 3 OK LOGIN completed"

## hmailserver_2020-03-03.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.14
* 192.168.100.11

**Users:**
3/3
* RoyTenneman@Giacobeville.com
* soniatheodore@giacobeville.com
* HelenJackson@Giacobeville.com

**Logins:**
* "IMAPD"	5708	2	"2020-03-03 12:14:34.694"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5708	2	"2020-03-03 12:14:34.931"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5712	4	"2020-03-03 12:31:31.176"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5712	4	"2020-03-03 12:31:31.250"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5712	5	"2020-03-03 12:31:54.241"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5712	5	"2020-03-03 12:31:54.322"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5708	6	"2020-03-03 12:31:55.673"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5708	6	"2020-03-03 12:31:55.829"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5696	7	"2020-03-03 12:32:28.040"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5696	7	"2020-03-03 12:32:28.118"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5688	3	"2020-03-03 12:32:37.985"	"192.168.100.14"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5704	8	"2020-03-03 12:32:50.541"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5704	8	"2020-03-03 12:32:50.990"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5712	10	"2020-03-03 12:33:28.118"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5712	10	"2020-03-03 12:33:28.555"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5696	11	"2020-03-03 12:33:46.593"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5696	11	"2020-03-03 12:33:46.651"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5692	12	"2020-03-03 12:33:47.416"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5692	12	"2020-03-03 12:33:47.449"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5692	13	"2020-03-03 12:34:05.936"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5692	13	"2020-03-03 12:34:05.989"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5704	14	"2020-03-03 12:34:07.625"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5704	14	"2020-03-03 12:34:07.687"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5708	9	"2020-03-03 12:34:25.859"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5704	15	"2020-03-03 12:34:57.381"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5704	15	"2020-03-03 12:34:57.485"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5688	16	"2020-03-03 12:35:39.000"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5704	17	"2020-03-03 12:36:03.738"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5704	17	"2020-03-03 12:36:03.777"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5704	19	"2020-03-03 12:37:59.871"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5704	19	"2020-03-03 12:37:59.912"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5684	20	"2020-03-03 12:38:09.143"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5684	20	"2020-03-03 12:38:09.186"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5708	18	"2020-03-03 12:43:08.106"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5708	21	"2020-03-03 12:43:20.887"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5708	21	"2020-03-03 12:43:20.949"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "IMAPD"	5704	23	"2020-03-03 12:43:39.444"	"192.168.100.21"	"RECEIVED: 3 login "RoyTenneman@Giacobeville.com" ***"
* "IMAPD"	5704	23	"2020-03-03 12:43:39.481"	"192.168.100.21"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5692	22	"2020-03-03 12:46:57.902"	"192.168.100.11"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5708	24	"2020-03-03 12:47:10.406"	"192.168.100.11"	"RECEIVED: 3 login "HelenJackson@Giacobeville.com" ***"
* "IMAPD"	5708	24	"2020-03-03 12:47:10.440"	"192.168.100.11"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5700	25	"2020-03-03 12:47:57.963"	"192.168.100.14"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"
* "IMAPD"	5684	26	"2020-03-03 12:48:14.448"	"192.168.100.14"	"RECEIVED: 3 login "soniatheodore@giacobeville.com" ***"
* "IMAPD"	5684	26	"2020-03-03 12:48:14.496"	"192.168.100.14"	"SENT: 3 OK LOGIN completed"
* "SMTPD"	5676	27	"2020-03-03 12:48:20.216"	"192.168.100.21"	"SENT: 250-giacobeville.com[nl]250-SIZE 20480000[nl]250-AUTH LOGIN PLAIN[nl]250 HELP"

**Interesting Logs (I think)**
* "APPLICATION"	5588	"2020-03-03 12:34:37.916"	"SMTPDeliverer - Message 172670: Delivering message from HelenJackson@Giacobeville.com to soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{31EC0802-8EFB-45AB-BE53-0C011D967497}.eml"
* "APPLICATION"	5588	"2020-03-03 12:35:51.081"	"SMTPDeliverer - Message 172672: Delivering message from HelenJackson@Giacobeville.com to RoyTenneman@Giacobeville.com, DouglasAdams@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{3DB2BEC5-D7E7-43DF-98FF-4DDBC0E9ED64}.eml"
* "APPLICATION"	5588	"2020-03-03 12:43:20.689"	"SMTPDeliverer - Message 172675: Delivering message from RoyTenneman@Giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{F2B0A721-8196-451E-940C-B7EEF17BE3BB}.eml"
* "APPLICATION"	5588	"2020-03-03 12:47:09.471"	"SMTPDeliverer - Message 172677: Delivering message from HelenJackson@Giacobeville.com to soniatheodore@giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{EA85ECFE-7D8E-4F64-9EA2-ED5D1F69423A}.eml"
* "APPLICATION"	5588	"2020-03-03 12:48:09.628"	"SMTPDeliverer - Message 172679: Delivering message from soniatheodore@giacobeville.com to MikeGold@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{CF8D9C1E-9D5C-4EE1-8262-C72F33AD95D4}.eml"
* "APPLICATION"	5588	"2020-03-03 12:48:33.025"	"SMTPDeliverer - Message 172681: Delivering message from RoyTenneman@Giacobeville.com to ThomasFord@Giacobeville.com, SoniaTheodore@Giacobeville.com, ShirleyAbdulla@Giacobeville.com, RonSwanson@Giacobeville.com, MillyBond@Giacobeville.com, MikeGold@Giacobeville.com, michaelscott@Giacobeville.com, MargaretMartinez@Giacobeville.com, HelenJackson@Giacobeville.com, DavidMcFarlane@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{EEB88A0D-A27C-4A9B-9384-E7D1933DE9CE}.eml"
* "APPLICATION"	5588	"2020-03-03 12:32:50.469"	"SMTPDeliverer - Message 172668: Delivering message from soniatheodore@giacobeville.com to HelenJackson@Giacobeville.com. File: C:\Program Files (x86)\hMailServer\Data\{348C588D-644C-4E00-A5E2-BD71802C0C83}.eml"***

### Status Report 2 ###

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
