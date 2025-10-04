# OSINT Challenge — "Starbucks Domain"

## 🧭 Executive Summary
I got a free "Venti Pumpkin Spice Latte" for checking their subdomains. I found one interesting but the responsible person only speaks French. Which subdomain I'm talking about?

## 🧰 Methodology
Clearly the company we are talking about is Starbucks. First of all, we will try to use the tool DnsDumpster.com which can discover hosts related to a domain. After using it on starbucks.com we discover its related domains and their IP addresses. Since the responsible person only speaks French, its safe to assume that it is based in a country where French is the official language (or one of them). If we scroll down the list of domains we end up with one that is based on Canada. The flag is this subdomain: “fb1.starbucks.com”.

## 🧩 Lessons Learned
Combine subdomain discovery with geolocation to infer locale-specific services.

## 🧠 Tags
'#DNS' '#DNSDumpster' '#Recon' '#Enumeration'

