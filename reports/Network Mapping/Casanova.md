# OSINT Challenge — "Casanova"

## 🧭 Executive Summary
My service is running on kenobi.hackingarena.com, port 9393. My name is Casanova. I bet you can't figure out my password I am very careful (except for this emberassing Ashley Madison case).

## 🧰 Methodology
First of all we run a port scan on port 9393 of the kenobi.hackingarena.com domain to see the service running there (nmap -sT kenobi.hackingarena.com -p9393 -Pn) and after it seeing it open but unknown we can try the version identifier or nc kenobi.hackingarena.com 9393 to  figure out that the service is ssh. Secondly, we see that the user refers to the Ashley Madison data breach case so we can readily assume that his password is one of those that were compromised in the attack. So we create a dictionary out of the top 100 passwords used on the site. Then we use this file (123.txt in this case) with a brute force tool such as hydra (hydra -l Casanova -P 123.txt kenobi.hackingarena.com ssh -s 9393). The result of the brute force operation is the password “kazuga”. Now, we use this password to login via ssh (ssh kenobi.hackingarena.com -p9393 -l casanova). We use ls to see files and we find the file flag. “more flag” reveals the contents of the flag file which is the flag of this task: “Hacking-Arena{I_am_much_more_Casan0va}”.

## 🧩 Lessons Learned
Using breached password lists and targeted brute-force tools is effective in lab environments.

## 🧠 Tags
'#ssh' '#hydra' '#bruteforce' '#mapping'

