# Security2

(P1) Create and maintain a professional diagram that documents your team's architecture.
Expect to deploy services such as web, proxy, and site-to-site access in your DMZ.
Expect to deploy services such as DB, IDS, or 802.1x in your secure zone.
Expect to use your inside zone hosts for staging, testing, or operating the services that you deploy to other zones.
Tag each asset in your diagram with OSI model information (layers 2, 3, 4, 7).

(P2) Configure the PA Firewall and deploy at least one Windows 2019 server and at least one Linux server (CentOS 8 or Ubuntu 20 LTS) in each zone (secure, inside, DMZ).
Follow our agreed class naming convention for your servers.
Verify that each pair of machines in each zone can ping each other.
 Configure administrator accounts, sub-interfaces, routing, rules, and NAT functionality on your Internet-facing firewall, sufficient for your DMZ and inside servers to access the Internet and receive OS updates. Also, configure appropriate static routes and access-rules/access-policies on both firewalls, so that you can remotely access and administer your servers across zone boundaries.
Deploy NLB Webservers and a web page in your DMZ that allows internet users to access your website. Stop one page and verify the other loads.
Example evidences that this milestone is complete: Screenshots that show pings work across zones and to the Internet, that the DMZ and inside servers are up to date. Screenshots that show your load balanced web-server functions correctly.
Your firewall rules should *block* DMZ and inside hosts to access the Secure Zone.

(P3) Deploy and proxy servers in the DMZ that relay DNS and web protocols, sufficient for your team's secure hosts to access the Internet and receive OS updates. 
Example DNS proxy services: Acrylic on Windows Server or Unbound on Linux
Example web proxy services: Squid on Linux, various proxy packages on Windows, modified nginx on Windows or Linux.
Evidences: nslookup DNS client works on secure machines, web browsing works on secure machines, and you can download and install OS updates to your secure machines.

(P4) Configure a remote-access VPN capability on your Internet-facing firewall that lets you remotely access your team's inside hosts.

(P5) Configure Multifactor VPN (DUO, FreeRadius)

(P6) Configure a NIDS sensor, managed from your secure zone, that monitors DMZ network traffic, and alerts when it notices potentially malicious traffic.  Add webservers and publish a website to monitor with the SEIM.

(P7) Configure an SNMP poller, managed from your secure zone, that monitors your firewalls' subinterfaces.

(P8) Configure a log manager or SIEM to receive and process application logs and events.

(P9) Complete the Penetration Testing exercise, as a team and/or in concert with partner teams.