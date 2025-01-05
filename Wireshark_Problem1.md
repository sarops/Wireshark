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
