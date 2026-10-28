Cybersecurity-Incident-Report-Network-Traffic-Analysis
DNS and ICMP Incident Report
This report explains why customers of a client company could not open its website between 1:24 PM and 1:28 PM. They saw a "destination port unreachable" error after waiting for the page to load, and they reported it to the company, which is how the IT team found out about the problem.
The IT team used tcpdump to capture the network traffic and found that the computer was sending DNS queries over UDP to port 53 to look up the IP address of yummyrecipesforme.com. Each time, the DNS server replied with an ICMP error saying "udp port 53 unreachable." The same error appeared three times in the log, which shows that nothing was listening on the DNS server's port 53.
Because the browser could not turn the website name into an IP address, the page never loaded. The most likely cause is that the DNS service on the server was unavailable, or that UDP port 53 was being blocked.
