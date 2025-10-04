# OSINT Challenge — "Beatles Login"

## 🧭 Executive Summary
Find the user: http://vader.hackingarena.com:825

## 🧰 Methodology
The first step in such tasks is to obtain the cookies (“beatlesid”) of the users that we have credentials of. We login with each of them and retrieve the values: “10303, 11161, 15803”. 

We now have two options, the first one is to brute force all numbers from 0 to 20000 in hope that this is the range in which possible cookies are found. This is, however, quite a big list and would take too long on burpsuite (we could use a faster alternative like OWASP ZAP). 

The second option is to try and figure out the relationship between the cookies and maybe infer a second, smaller, wordlist which we can use as a more efficient dictionary for our attack. Indeed, after studying the possible relationships between the numbers we finally figure out that they are primes. So do we compile a wordlist which comprises of all prime numbers up to 20000 to use in the intruder. 

We can either set up a filter in the intruder or monitor the response size in order to single out the ones that contain actual sessions. 

This process results in the known three cookies and another, new, one: “17159”. Upon changing the GET request and using 17159 as the beatlesid, we are met with a page which contains the flag for this task: “Hacking-Arena{Prime_days_a_week}”.


## 🧩 Lessons Learned
Patterns in artifacts (cookies, IDs) often imply mathematical properties; testing hypotheses reduces search space.

## 🧠 Tags
'#Cookies' '#OWASPZAP' '#BurpSuite' '#ctf'

