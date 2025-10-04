# OSINT Challenge — "Web Form"

## 🧭 Executive Summary
Can you find the flag in this simple webpage with just a search bar? http://padawan.hackingarena.com:820?


## 🧰 Methodology
We notice straight away that the webpage has a search bar, and we know that after normal use, if the website is dynamic our methodology states that we should follow with unintended content. Forcing a 404 gets us nowhere but, by inspecting the html source we see that the form has an input limit size of 70 so we enter a query that surpasses this limit. This is met with the message “Error in name processing /var/www/partnerprocess/process.php” which betrays the existence of a “partnerprocess” folder. This folder is indeed accessible and in it lies a text file named flag.txt which contains the flag for this task: “UiO-Hacking-Arena{Err0r_m4ssag4_d1scl0sure}”. 

## 🧩 Lessons Learned
Using breached password lists and targeted brute-force tools is effective in lab environments.

## 🧠 Tags
'#webhacking' '#php' '#bruteforce' '#mapping'

