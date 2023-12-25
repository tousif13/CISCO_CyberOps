# CA Skills Assessment

> Analyzing and reporting my findings of a pcap file (Tousif.pcap) using Security Onion.

* Importing the pcap file in Security Onion.

      sudo so-import-pcap Tousif.pcap

![importpcap](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/000db938-5fb3-4ab8-bf8b-e7e2b2ff054a)

* After analyzing the traffic with Snort and Zeek, it processed the pcap dates through 03-12-21 and provided kibana link to view data.
* Opening kibana and giving absolute time range from `2021-12-03` to `2021-12-04`.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/9d6c3f37-aeb1-4bcf-bb54-f407336cf5df)

* After updating the time range, we can see 4,316 logs appeared in the given range of time.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/e05d55b6-2e34-482e-b26d-b4eb487dce40)

## Zeek Notices

* Let's see the Zeek notices window first.
* We got 7 Zeek notices as shown below.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/607d5e73-3a3d-4993-b31f-a584f190f436)

* Zeek notified about SSL Invalid server certificate and a signature match of `TeamCymruMalwareHashRegistry`.
* In Zeek Message/Sub-message, we can see a detailed inspection of Zeek notices.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/78701a66-7743-486d-b2f9-7b67055a359f)

* Malware Hash Registry Detection rate is of 24%.
* Thus, we're dealing with a malware infiltrate which lead to failure of SSL certification validation.
* Let's see through the NIDS alerts window as it involves SSL certificate validation failures.

## NIDS alerts

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/d1c466e2-7e37-46d1-a7f2-833565c579cb)

* We got 45 NIDS alerts in this period of time and the classification is given such as `misc-activity`, `policy-validation`, `trojan-activity` etc.
* Let's see the NIDS alerts.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/c1f7615b-d9db-42f4-8644-fa7f8453271a)

* There are some alerts like first three which depicts about HTTP connection is made by which an executable is downloaded which is a `.dll` file.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/c5249047-d471-4be5-bad3-d13592c549d2)

* As shown above, a dll file called `IE7MnYfF4c.dll` is attached.
* Extract the file either through `Wireshark` or `NetworkMiner`. Using NetworkMiner in this case.

![dll](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/5acbab76-5bd5-4e73-8bbb-0e9e9548d9e1)

* Uploading and checking the dll file in `VirusTotal`.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/1dd316dd-0cc6-407f-bfd7-0e4b67c7eab7)

As guessed already, it is indeed a malicious dll file which got flagged by 57 out of 71.
