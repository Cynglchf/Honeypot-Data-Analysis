# CVE Analysis

This section presents an analysis of the CVE (Common Vulnerabilities and Exposures) entries detected in the honeypot environment showing the most frequently observed CVEs based on the collected data.

#### Suricata CVE - Top 10

| CVE(s) | Count | Description |
| --- | --- | --- |
| [CVE-2002-0013](https://www.cve.org/CVERecord?id=CVE-2002-0013) / [CVE-2002-0012](https://www.cve.org/CVERecord?id=CVE-2002-0012) | 19 | **CVE-2002-0013:** SNMPv1 request-handling vulnerability allowing remote denial of service or privilege escalation. <br> **CVE-2002-0012:** SNMPv1 trap-handling vulnerability allowing remote denial of service or privilege escalation |
| [CVE-2002-0013](https://www.cve.org/CVERecord?id=CVE-2002-0013) / [CVE-2002-0012](https://www.cve.org/CVERecord?id=CVE-2002-0012) / [CVE-1999-0517](https://www.cve.org/CVERecord?id=CVE-1999-0517) | 14 | **CVE-1999-0517:** SNMP vulnerability due to default, null or missing community names. | 
| [CVE-2001-0414](https://www.cve.org/CVERecord?id=CVE-2001-0414) | 9 | Buffer overflow in ntpd allowing remote denial of service or possible arbitrary code execution via a long readvar argument. |
| [CVE-2019-11500](https://www.cve.org/CVERecord?id=CVE-2019-11500) | 2 | Dovecot and Pigeonhole mishandle '\0' in quoted strings, potentially causing out-of-bounds writes and remote code execution. |
| [CVE-2024-3721](https://www.cve.org/CVERecord?id=CVE-2024-3721) | 2 | TBK DVR devices allow remote OS command injection via the mdb/mdc parameter in /device.rsp. |
| [CVE-2024-4577](https://www.cve.org/CVERecord?id=CVE-2024-4577) / [CVE-2002-0953](https://www.cve.org/CVERecord?id=CVE-2002-0953) | 2 | **CVE-2024-4577:** PHP CGI argument injection vulnerability on Windows systems. </br> **CVE-2002-0953:** PHP application vulnerability allowing remote arbitrary PHP code execution via improperly handled parameters. |
| [CVE-2024-4577](https://www.cve.org/CVERecord?id=CVE-2024-4577) | 2 | PHP CGI argument injection vulnerability on Windows systems. |
| [CVE-2005-4050](https://www.cve.org/CVERecord?id=CVE-2005-4050) | 1 | Buffer overflow vulnerability in Multi-Tech MultiVOIP devices allowing remote code execution. |
| [CVE-2006-2369](https://www.cve.org/CVERecord?id=CVE-2006-2369) | 1 | RealVNC-based systems may allow remote authentication bypass due to acceptance of insecure security types. |
| [CVE-2017-3506](https://www.cve.org/CVERecord?id=CVE-2017-3506) / [CVE-2017-3606](https://www.cve.org/CVERecord?id=CVE-2017-3606) | 1 | **CVE-2017-3506:** Oracle WebLogic Server may allow unauthenticated remote access leading to unauthorized modification or disclosure of application data. <br> **CVE-2017-3606:** A local interaction‑dependent vulnerability in Oracle Berkeley DB that can lead to full Data Store compromise. |

The analysis of CVE entries shows that vulnerabilities are still being scanned widely and automatically including those published between 1999 and 2002. Most observed attacks targeted older vulnerabilities, particularly in SNMP services, but targeted attempts were also made against more modern systems which indicates that attackers use systematic and automated scanning methods covering both the oldest and the most recent known vulnerabilities. 

This pattern strongly indicates the use of automated mass-scanning where attackers or botnets run large CVE signature lists against any reachable IP address. The fact that the honeypot was online only for a short period of time further supports the idea that attackers target any IP they can find.
