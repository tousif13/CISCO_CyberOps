# CA Skills Assessment

> Analyzing and reporting my findings of a pcap file (Tousif.pcap) using Security Onion.

* Importing the pcap file in Security Onion.

      sudo so-import-pcap Tousif.pcap

![importpcap](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/000db938-5fb3-4ab8-bf8b-e7e2b2ff054a)

* After analyzing the traffic with Snort and Zeek, it processed the pcap dates through 03-12-21 and provided kibana link to view data.
* Opening kibana and giving absolute time range from `2021-12-03` to `2021-12-04`.

![image](https://github.com/tousif13/CISCO_CyberOps/assets/33444140/9d6c3f37-aeb1-4bcf-bb54-f407336cf5df)

* After updating the time range, we can see 4,316 logs appeared in the given range of time.

