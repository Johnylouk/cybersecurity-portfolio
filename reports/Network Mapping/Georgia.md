# OSINT Challenge — "Georgian Mail Server"

## 🧭 Executive Summary
Find a mail server that is related to the Georgian government in the 5.44.0.0/16 range.

## 🧰 Methodology
Running nmap list scan which asks the DNS and simply lists the targets to scan on 5.44.0.0/16 while at the same time searching the output for Georgian governmental sites leads us to the answer. The command we run is “nmap -sL 5.44.0.0/16 | grep gov.ge” and in its output it is easy to discern which of the domains pertains to a mail server. The flag is: “mail.cloud.gov.ge”. 

## 🧩 Lessons Learned
Passive DNS listing techniques are suitable when instructed not to connect to hosts.

## 🧠 Tags
'#DNS' '#NetworkMapping' '#Recon' #Enumeration

