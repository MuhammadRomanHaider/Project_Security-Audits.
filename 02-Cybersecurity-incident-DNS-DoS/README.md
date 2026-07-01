# Incident Report: Network Traffic Analysis (Suspected DNS DoS)

## Project Overview:
This project is the google cybersecurtiy course activity which involves a security analysis of network traffic logs following a service disruption. As part of a cybersecurity incident response simulation, `tcpdump` logs were analyzed to determine why users were unable to access a client website, identifying a critical failure in DNS resolution.

## Scenario Details:
* **Target Website:** www.yummyrecipesforme.com
* **Reported Symptom:** Users experienced long page load times followed by a "destination port unreachable" error.
* **Analysis Tool:** `tcpdump`
* Image:

   <img width="1608" height="687" alt="Scenario" src="https://github.com/user-attachments/assets/8f5824f8-9eb9-4f07-a416-b40171b58d79" />

---

### Network Log Evidence Image:
Below is the packet capture showing the client's DNS query and the subsequent ICMP unreachable error response:

<img width="1561" height="771" alt="Event log" src="https://github.com/user-attachments/assets/77a6ee70-4313-48e5-b6a8-ddee3ba33a37" />


---

## Incident Analysis:

### Part 1: Provide a summary of the problem found in the DNS and ICMP traffic log.
The network traffic analyzer (tcpdump) indicate that port 53 is unreachable when attempting to reach yummyrecipesforme.com website through UDP protocol to the DNS server, port 53 is normally used for DNS service, protocols used here are UDP and ICMP, This is based on the results of the network analysis, which shows that the ICMP(Used for Error report delivery) returned the error message: "udp port 53 unreachable". This indicates that UDP request for IP address to DNS server is not going through because the port 53 is unreachable, resulting in no service being provided.

### Part 2: Explain your analysis of the data and provide at least one cause of the incident.
Time at which the incident occurred is at 1:24 p.m., after which the clients' customers reported of not being able to reach the website and after long wait for page to load and error appeared stating "destination port unreachable". After being aware of the situation the IT team first tried to visit the website and received the same error, after which the team loaded network analyzer tool, tcpdump and visited the web site again, which sent a UDP request to DNS server which came back with ICMP error stating port 53, which is a DNS service request, is unreachable. So the UDP request for IP address is not going through DNS server because there is no service at the port 53. Due to which the DNS service remains unavailable, and the website is currently inaccessible to users. The next steps would be to inform security engineers to troubleshoot why the DNS service is down by reaching out to DNS service provider, checking for possible DoS attack, firewall configurations or incorrect server settings. 

It is highly possible that this is the indication of a DoS attack on DNS server and less likely the possibility of issues with firewall configuration or server settings with DNS Server.

---

## Skills Demonstrated
* Network Traffic & Packet Analysis (`tcpdump`)
* Incident Response Documentation
* Protocols Audited: DNS, UDP, ICMP
* Root Cause Analysis (DoS Identification)
---

## Document:
[Cybersecurity incident report network traffic analysis...pdf](https://github.com/user-attachments/files/29555477/Cybersecurity.incident.report.network.traffic.analysis.pdf)
