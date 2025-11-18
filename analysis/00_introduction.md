# Introduction

This section provides a short overview of the collected data establishing a baseline for further analysis. It presents the total number of attacks recorded and illustrates how these events are distributed across the deployed honeypots without delving into detailed analyses.

This dataset consists of 11363 recorded attack events collected from a multi-honeypot deployment. Data was gathered continuously over a 10-hour period within a single day without interruptions. The environment included multiple honeypot services provided by [T-Pot](https://github.com/telekom-security/tpotce) hosted on an [Azure Virtual Machine](https://azure.microsoft.com) and the collected  data was analyzed and visualized using [Kibana](https://github.com/elastic/kibana).

The table below presents the distribution of attacks across the deployed honeypots, highlighting each honeypots relative share of the overall attack activity.

| Honeypot | Count | % of total attacks (11363) | Project link |
| --- | --- | --- | --- |
| Honeytrap | 3976 | 34,99% | [GitHub](https://github.com/armedpot/honeytrap/) |
| Cowrie | 3579 | 31,50% | [GitHub](https://github.com/cowrie/cowrie) |
| Dionaea | 3323 | 29,24% | [GitHub](https://github.com/DinoTools/dionaea) |
| Tanner | 120 | 1,06% | [GitHub](https://github.com/mushorg/tanner) |
| Redishoneypot | 80 | 0,70% | [GitHub](https://github.com/cypwnpwnsocute/RedisHoneyPot) |
| H0neytr4p | 70 | 0,62% | [GitHub](https://github.com/pbssubhash/h0neytr4p) |
| Sentrypeer | 61 | 0,54% | [GitHub](https://github.com/SentryPeer/SentryPeer) |
| ConPot | 38 | 0,33% | [GitHub](https://github.com/mushorg/conpot) |
| Mailoney | 35 | 0,31% | [GitHub](https://github.com/phin3has/mailoney) |
| Adbhoney | 27 | 0,24% | [GitHub](https://github.com/huuck/ADBHoney) |
| ElasticPot | 18 | 0,16% | [GitLab](https://gitlab.com/bontchev/elasticpot) |
| Ciscoasa | 16 | 0,14% | [GitHub](https://github.com/Cymmetria/ciscoasa_honeypot) |
| Honeyaml | 11 | 0,10% | [GitHub](https://github.com/mmta/honeyaml) |
| Heralding | 6 | 0,05% | [GitHub](https://github.com/johnnykv/heralding) |
| Ipphoney | 3 | 0,03% | [GitLab](https://gitlab.com/bontchev/ipphoney) |

  
From this point forward the data collected from the honeypots is presented and analysed.
