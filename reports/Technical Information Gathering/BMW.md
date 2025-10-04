# OSINT Challenge — "BMW

## 🧭 Executive Summary
Find the /24 BMW-NET in Munich. The flag is in CIDR format.

## 🧰 Methodology
First of all, we will try to use the tool DnsDumpster.com which can discover hosts related to a domain. After using it on bmw.com we discover its related domains and their IP addresses. We select one (the first) that is based in Germany and run a WhoIs (from ViewDns.info) on it. Thus is the IP 212.18.3.8 resolved to belong in a network of 212.18.3.0 - 212.18.3.255 which indeed, written in CIDR format is /24. The flag is the CIDR format of said network: “212.18.3.0/24”. 

## 🧩 Lessons Learned
Combine DNS enumeration with regional filtering and WHOIS to map org-owned ranges.

## 🧠 Tags
'#DNS' '#DNSDumpster' '#Recon' '#Enumeration'

