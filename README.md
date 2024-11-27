
Cybersecurity Incident Report
========================================
Project Description:
--------------------------------------------------------------------------------
This report documents the investigation and analysis of a cybersecurity incident involving 
DNS and ICMP traffic. The incident occurred when users were unable to access a website 
(www.yummyrecipesforme.com), encountering an error message indicating that the destination 
port was unreachable. Using network protocol analysis with tcpdump, the issue was traced to 
a DNS server failure potentially caused by misconfiguration or a Denial of Service (DoS) attack. 
This report outlines the problem, analysis, findings, and recommended next steps.


Part 1: Summary of the problem found in the DNS and ICMP traffic log
--------------------------------------------------------------------------------
The network protocol analyzer logs indicate that UDP port 53 is unreachable when attempting to access the website www.yummyrecipesforme.com. 
Port 53 is used for DNS traffic, which resolves domain names into IP addresses. This error indicates that DNS requests to resolve the website's 
IP address were unsuccessful. The issue may be caused by a misconfigured or offline DNS server or a potential Denial of Service (DoS) attack 
targeting the DNS service.


Part 2: Explanation of analysis and cause of the incident
-------------------------------------------------------------------------------
The incident occurred at 1:24:32 p.m., as indicated by the timestamps in the tcpdump logs.
Customers reported being unable to access the website and receiving the error message "destination port unreachable." IT analysts replicated the issue 
and used tcpdump to capture and analyze network traffic.

Actions taken by the IT department to investigate the incident:
- Analyzed DNS and ICMP traffic using the tcpdump tool.
- Observed outgoing UDP packets sent to the DNS server's port 53, followed by ICMP error responses indicating that port 53 was unreachable.
- Confirmed repeated ICMP error messages from the DNS server to the client IP.

Key findings of the IT department’s investigation:
- DNS server at IP address 203.0.113.2 was unresponsive to queries.
- The browser sent UDP packets to resolve the IP address for the domain, but the DNS server returned ICMP error messages indicating "udp port 53 unreachable."
- Multiple attempts to contact the DNS server resulted in the same error.

Likely cause of the incident:
The DNS server may have been misconfigured, offline, or targeted by a Denial of Service (DoS) attack, which could prevent it from responding to legitimate DNS queries.

Next Steps:
--------------------------------------------------------------------------------
- Confirm whether the DNS server is under a DoS attack by analyzing traffic for excessive volume.
- Contact the DNS server administrator to check for misconfigurations or system outages.
- Implement mitigation strategies such as load balancing or redirecting traffic to backup DNS servers to restore functionality.

========================================

Prepared on: 2024-11-27 23:33:45
