# Credential Analysis


The analysis of used credentials utilized data collected from a [Cowrie](https://github.com/cowrie/cowrie) honeypot. [Cowrie](https://github.com/cowrie/cowrie) is an interactive honeypot system that emulates SSH and Telnet services to lure attackers and record their activity. The dataset includes attempted usernames, passwords and the frequency of login attempts.
# Attempted Usernames

The dataset shows that attempted usernames were generally common default or administrative accounts indicating the use of automated brute force tools. The table below summarizes the most frequently observed usernames and their occurrence counts in the analysed dataset:

  

| Username | Count |
| --- | --- |
| admin | 49 |
| root | 43 |
| backup | 27 |
| centos | 27 |
| ec2-user | 27 |
| mysql | 27 |
| nginx | 27 |
| postgres | 24 |
| pi | 19 |
| es | 18 |
| ftp | 18 |
| guest | 18 |
| newuser | 18 |
| oracle | 18 |
| tempuser | 18 |
| test | 18 |
| ubuntu | 18 |
| user | 18 |
| admin1 | 9 |
| apache | 9 |
| debian | 9 |
| deploy | 9 |
| developer | 9 |
| docker | 9 |
| dspace | 9 |
| fedora | 9 |
| ftpuser | 9 |
| git | 9 |
| mongodb | 9 |
| nagios | 9 |
| operator | 9 |
| redhat | 9 |
| redis | 9 |
| svn | 9 |
| tomcat | 9 |
| weblogic | 9 |
| webmaster | 9 |
| www | 9 |
| www-data | 9 |
| administrator | 8 |
| sa | 8 |
| stefanie | 4 |
| (empty) | 2 |

  

Results were compared against a small but widely used and publicly available list from the [SecLists](https://github.com/danielmiessler/SecLists)-project "top-usernames-shortlist.txt" which contains commonly used usernames often employed in penetration testing. The comparison indicates that most usernames observed in our dataset are included in this list, supporting the observation that attacks primarily targeted common default and administrative accounts. No percentage comparison was made, as the reference list is significantly smaller than our dataset and does not provide a reliable relative metric. The comparison was intended solely to confirm that the usernames used are widely known rather than to provide a relative metric.

# Attempted Passwords

Attempted passwords were mostly simple and easily guessable. The table below lists the most common exposed passwords. Less common or more complex passwords have been anonymized with *** for safety and privacy, but more common passwords (including many from wordlists such as rockyou.txt) are shown because they are publicly known and trivially simple. These observations suggest that the attacks largely relied on automated brute force techniques leveraging known usernames and common passwords. The table below summarizes the most frequently observed passwords and their occurrence counts in the analysed dataset:


  
| Password | Count |
| --- | --- |
| password | 47 |
| 111111 | 45 |
| 123123 | 45 |
| 12345 | 45 |
| 12345678 | 45 |
| 123456789 | 45 |
| qwerty | 45 |
| 123456 | 44 |
| 1234567 | 27 |
| 000000 | 18 |
| 123 | 18 |
| 1234 | 18 |
| 1q2w3e4r | 18 |
| 654321 | 18 |
| P@ssw0rd | 18 |
| passw0rd | 18 |
| password1 | 18 |
| (empty) | 14 |
| admin | 8 |
| postgres | 7 |
| *** | 4 |
| root | 4 |
| centos | 2 |
| ubuntu | 2 |
| warrior1 | 2 |
| 5404 | 1 |
| 554455 | 1 |
| 555888 | 1 |
| 56835683 | 1 |
| 68camaro | 1 |
| 741236 | 1 |
| 789123456 | 1 |
| 852654 | 1 |
| 88888888 | 1 |
| *** | 1 |
| 951159 | 1 |
| 96385274 | 1 |
| 9669 | 1 |
| Admin123 | 1 |
| Admin@123 | 1 |
| Wq | 1 |
| a123321 | 1 |
| abcd1234 | 1 |
| aces | 1 |
| acoustic | 1 |
| acura1 | 1 |
| admin123 | 1 |
| adonai | 1 |

  


Attempted passwords observed in the attacks were similarly compared against the publicly available rockyou.txt wordlist using exact string matching. Rockyou.txt is an extensive collection of leaked passwords and therefore the comparison was not intended to produce a relative metric. Instead it served only to determine whether the passwords seen in the dataset also appear in this well-known corpus of leaked credentials. Of the 47 unique passwords observed in the dataset 43 were found in rockyou.txt. The four passwords not present in the list are shown in the table below with two entries have been anonymized (***) for safety.

  

| Password | Count |
| --- | --- |
| *** | 4 |
| centos | 2 |
| *** | 1 |
| Wq | 1 |

  

# Username and Password Combinations

According to the honeypot data attackers mostly tried combinations of simple, publicly known passwords and usernames. Only a small fraction of attempts involved less common or more complex passwords which highlights the importance of basic security measures such as avoiding default usernames and using strong complex passwords.

In this project the honeypot received a high volume of attacks simply because it was exposed to the public internet with open ports. This shows that using strong passwords and non-guessable usernames is especially important for small or lesser-known businesses as it greatly reduces the risk of successful attacks.

Note: Attackers often target real organizations by leveraging employees actual names or predictable username patterns. This makes it especially important to ensure that usernames are not easily guessable and maintain sufficient complexity, in addition to enforcing strong password policies.

The table below shows the passwords most frequently used in combination with the top three most common usernames:

  

| Username | Password | Count |
| --- | --- | --- |
| admin | admin | 2 |
| admin | *** | 2 |
| admin | password | 2 |
| root | admin | 6 |
| root | root | 4 |
| root | *** | 2 |
| backup | password | 2 |
| backup | qwerty | 2 |
| backup | 12345 | 2 |

  

Unusual password was used with both admin and root usernames from two distinct source IPs. The password does not appear in SecLists or other public lists, so it is not disclosed here. The IPs from China and the United States made the attempts exactly one hour apart suggesting an automated scan of public IPs.

This indicates that the attacker likely attempted to use a leaked or guessed password against public IP addresses using automated tools.

# Conclusion

The analysis shows that attackers mostly attempted simple publicly known usernames and passwords. Only a small fraction of attempts involved less common or more complex credentials. Usernames were generally easy to guess emphasizing the need for non-guessable usernames alongside strong and complex passwords. The data also indicates that exposing public IPs with open ports significantly increases the likelihood of being targeted by attackers.

Since attackers targeting real-world organizations often leverage employees actual names and predictable username patterns this data underscores the importance of enforcing both complex usernames and strong password policies.
