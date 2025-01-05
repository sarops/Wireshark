## Wireshark Problem Scenarios

#Problem 1: Unusual Network Traffic Identification

Scenario: Network performance has degraded significantly in the past few weeks in a company, as noticed by the network administrator.
Users have been experiencing slow connectivity, and some applications are timing out.
There is a suspicion that there are unusual traffic patterns in action and/or potential unauthorized network access.

1) Open Wireshark on the device connected to the network.
Use a capture filter to limit the data to traffic relevant to the traffic that needs to be analyzed (for example, tcp.port == 80 for HTTP traffic).



2) When enough data has been captured, the capture can be stopped.
Enter the packet analyzing phase; The various indicators of unusual activity can be High Traffic Volume, Unusual Protocols and Suspicious IP Addresses. All three can be investigated by the use of the Statistics menu.



“IO Graphs” can help visualize traffic over time, and spikes that deviate from normal traffic patterns can appear (High Traffic Volume).

"Protocol Hierarchy" checks for unknown or unexpected protocols. If there are any protocols not typically used in the work environment, this can be further investigated (Unusual Protocols).

"Statistics" helps identify any unfamiliar IP addresses generating substantial amounts of traffic and/or communicating with internal devices (Suspicious IP Addresses).



3) Filter and Drill down traffic by the use of display filters. They help isolate traffic further through queries (for example, dns.qry name == "1.0.168.192.in-addr.arpa" && dns.qry.type == 12)
Any anomalies in the filtered results could e.g. indicate a potential DNS tunnelling attack if there are many DNS queries to an unkown domain.



4) Communication between devices should also be exclusively examined through "Statistics" > "Conversations" in order to check the duration and number of packets exchanged through excessive communication between devices. High values can indicate a DDoS attack or data exfiltration.



5) If any suspicious connections are identified, right-click on a packet and select "Follow" > "TCP Stream". This will show the entire conversation between two endpoints. The dialog box data can be viewed in several helpful formats (https://www.wireshark.org/docs/wsug_html_chunked/ChAdvFollowStreamSection.html).



6) Any and all key findings should be documented via the use of screenshots and other forms of capture. Writing up a report and summarizing said findings along with recommendations for further investigation and/or remediation steps is strongly advised.



7) After a thorough analysis is done, appropriate actions should be taken such as blocking suspicious IP addresses via the firewall, implementing stricter access controls and/or conducting a deeper forensic analysis if necessary.
Some tools in conjuction with Wireshark can enhance in the aforementioned forensic analysis, such as NetworkMiner (https://www.netresec.com/?page=NetworkMiner) and Suricata (https://suricata.io/).
