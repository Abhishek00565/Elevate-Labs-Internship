**Objective**
The main objective of this task was to discover open ports on devices within a local network to understand network exposure. The task focused on using network reconnaissance skills to identify active hosts and their services.

**Tools and Methodology**
Nmap 7.97: A free and open-source network scanner. The command used for the scan was nmap -sS 10.248.179.22/24, which performs a TCP SYN scan.


**Wireshark:** An optional but valuable tool for analyzing network traffic. Wireshark was used to observe the packets sent and received during the Nmap scan, specifically to confirm the TCP SYN scan process.

**Local Network and Scan Details**

**Local IP Range:** The IP range scanned was **10.248.179.22/24**.


**Nmap Scan Report**: The scan, which took 75.66 seconds, found four active hosts within the network.

**Scan Results:** Open Ports and Services
The scan identified several open ports on two of the active hosts.

**Host 10.248.179.51:**

**Port 53/tcp**: open, running the domain service. This is a DNS service.

**Host 10.248.179.126:**

**Port 135/tcp**: open, running msrpc (Microsoft Remote Procedure Call).

**Port 139/tcp**: open, running netbios-ssn (NetBIOS Session Service).

**Port 445/tcp:** open, running microsoft-ds (Microsoft Directory Services).

**Port 902/tcp:** open, running iss-realsecure.

**Port 912/tcp**: open, running apex-mesh.

**Port 2869/tcp**: open, running icslap.

**Wireshark Analysis**
Wireshark confirmed the Nmap process by showing SYN packets being sent to various ports on the target hosts. The captured traffic shows the scanner sending a packet with the SYN flag set to the destination port. The presence of these packets confirms that a TCP SYN scan was performed.

**Potential Security Risks**
Open ports can expose a network to potential security risks. For example, the open ports 139 and 445 on host.

10.248.179.126 are associated with Windows file and printer sharing. These services have been historically vulnerable to exploits and malware, such as WannaCry, making the host a potential target. Proper security measures, such as firewalls and regular patching, are essential to mitigate these risks.
