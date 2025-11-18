# Summary

### Attack Distribution

In this project I collected and analysed 11363 attack events from a multi-honeypot deployment over a 10-hour period. The attacks were distributed across the deployed honeypots with Honeytrap, Cowrie and Dionaea receiving the majority of events (~96%).

### Credential Analysis

Analysis of login attempts on the Cowrie honeypot revealed that attackers primarily attempted common usernames and simple publicly known passwords. The top usernames (admin, root) and passwords (123456, password) matched widely used public wordlists. Only a small fraction of attempts involved unique or complex credentials.

### Attacker Behavior

Attacker activity included extensive reconnaissance, removal of competing cryptominers and deployment of malicious files. Commands such as uname -a and cat /proc/cpuinfo show that attackers collected system and network information to identify vulnerable targets and assess mining suitability. Download and execution of multiple malicious binaries were fully automated, often with fallback methods to ensure at least one payload executed.

### Malware Analysis

Malware observed followed a two-stage process: the clean.sh shell script removed competing miners followed by execution of the Redtail cryptojacking malware. Redtail exploited system resources for cryptocurrency mining, established persistence through cron jobs, firewall rule modifications and obfuscated its code to evade detection.

### Common Vulnerabilities and Exposures Analysis

The most frequently targeted vulnerabilities were older SNMP and system-specific flaws though some modern vulnerabilities were also scanned. Automated mass-scanning across both old and new CVEs indicates that attackers or botnets target any reachable IP address.


# Conclusions

The honeypot deployment proved to be an effective tool for gathering detailed information on attacker behavior, methods and malware deployment. During the brief ten-hour observation period the system experienced a substantial number of attacks demonstrating that publicly accessible systems quickly attract automated scanning and exploitation attempts.

Analysis revealed that attackers relied on default usernames and weak passwords underscoring the critical importance of enforcing strong, non-default credentials for system protection. Brief exposure of a poorly secured system was sufficient to enable malware installation such as cryptominers which highlighted the speed and efficiency of automated attack campaigns.

The malware deployment occurred in two stages. First, any competing malware was identified and removed to ensure the attacker's malware could operate without interference. Then, the attacker's malware was installed and activated. This process highlights the competitive nature of attackers competing for limited system resources and supports the observation that publicly accessible systems quickly attract automated scanning and exploitation attempts as attackers seek to dominate vulnerable environments.

The vulnerabilities observed in the honeypot highlight the importance of continuous system maintenance and updates. While most attacks targeted older vulnerabilities some more recent vulnerabilities were used that allowed critical actions such as remote code execution, privilege escalation and authentication bypass. This underscores the need for regular patching and proactive security practices.

Overall, the project shows that even short-term exposure of unprotected systems can lead to rapid compromise underlining the need for strong credentials, timely updates and continuous system monitoring.
