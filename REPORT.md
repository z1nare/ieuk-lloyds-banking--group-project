# Investigation of Traffic Surge and Bot Mitigation for Lloyds Project
## Summary of Findings:
### An analysis of server logs confirms that recent server downtime is caused by high-volume, automated traffic from a small number of malicious actors, not legitimate users. This traffic appears to be a combination of aggressive content scraping and vulnerability scanning. Implementing immediate, low-cost security measures will block this traffic, stabilize the servers, and protect the website's performance for real subscribers.
## Key Findings
### The investigation revealed several key indicators of a targeted, automated attack:

- Concentrated Traffic Source: A disproportionate volume of traffic originates from a very small number of IP addresses. As shown in Figure 1, just 16 suspicious IPs account for thousands of requests, with the top 3 offenders being the most significant.

- Non-Human Behavior: The traffic patterns are clearly automated. The hourly request logs (Figure 2) show activity in unnatural, uniform spikes rather than the organic patterns expected from human users.

- Malicious Intent: A high frequency of requests resulting in 401 (Unauthorized), 403 (Forbidden), and 404 (Not Found) errors indicates that bots are actively probing for restricted endpoints and potential vulnerabilities. The use of user agents from known security tools like sqlmap, ZAP, and Burp Suite confirms this.

- Negative Server Impact: The thousands of 5xx server errors in the logs directly correlate this malicious traffic to the reported website downtime, confirming that the bots are overwhelming the server's resources.

#### Figure 1: Total requests per IP address, highlighting the top offenders. ![Plot showing logging activity of each IP. Last 5 IPs have the same amount of logging activity, top 3 IPs show significant difference in logging frequency compared to other IPs and the rest have similar amounts with slight differences.](plots/output1.png)

#### Figure 2: Hourly request frequency for suspicious IPs, showing non-human spike patterns. ![Second plot illustrates hourly activity of each IP. It is clear that every IP produces enormous logging booms during separate hours. Some of the IPs spike once and never appear again, while others produce the same amount of logs over certain hours, which is likely a pattern.](plots/output3.png) 

## Recommendations
### The following immediate actions are recommended to mitigate this threat:

   1. Rate-Limit and Block Abusive IPs: Implement a tool like fail2ban to automatically block IPs that generate excessive requests or repeated errors (401, 404, 5xx). Configure the web server (e.g., NGINX) to rate-limit requests to a reasonable threshold (e.g., 100 per minute).

   2. Filter Malicious User Agents: Block all requests from user agents associated with known hacking tools and scanners, including sqlmap, nikto, curl, and generic python-requests.

   3. Implement Geo-Blocking: As a secondary measure, consider blocking or throttling traffic from geographic regions that are common sources of attacks and are not part of your primary user base.

## Assumptions & Cost Analysis
This report assumes you have administrative access to your web server and can modify its configuration or install standard packages.
The proposed solutions are highly cost-effective. They rely on features already built into modern web servers or on free, open-source software (fail2ban). The primary cost will be the engineering time required for implementation, with no additional software licensing fees.
