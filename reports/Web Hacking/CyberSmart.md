# OSINT Challenge — "Beatles Login"

## 🧭 Executive Summary
Find the flag here: http://padawan.hackingarena.com:804

## 🧰 Methodology
The data we can extrapolate from such a simple page is limited, so we can try to take a look at the pre rendered php script of “index.php”. The way to do this is by tampering the variable “program” in the url with a php filter to encode the script in base64 like so: 

http://padawan.hackingarena.com:804/index.php?program=php://filter/convert.base64-encode/resource=index.php

Now we can use a base64 decoder and try to view the original php script for more clues. Indeed, we find out that there is a comment that leaks information that the thing we are looking for is in the folder “/etc/secretsmartcyber/flag”. 

Once more unto the breach with url tampering but this time we use the aforementioned file in the variable in order to read it (assuming the apache user has read permissions on it) like so:

http://padawan.hackingarena.com:804/index.php?program=/etc/secretsmartcyber/flag

The flag is resolved to be: 

“Hacking-Arena{L0cal_f1les_sh0uld_n0t_supp0s4d_t0_b4_v1s1bl4}”

## 🧩 Lessons Learned
PHP wrappers enable disclosure; limit file inclusion and sanitize input to avoid LFI/FFI.

## 🧠 Tags
'#PHP' '#Exfiltration' '#Base64' '#ctf'

