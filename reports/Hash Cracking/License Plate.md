# OSINT Challenge — "License Plate"

## 🧭 Executive Summary
I know this guy (lives in Norway) always has his license plate as the password, but I only know the hash: 3c15ee9710f7b56906cb33429d636de6 What's his password?

## 🧰 Methodology
First of all, we may begin by setting our hash into a txt file called hash.txt. Now, since we know that the password is a Norwegian license plate, we know that it is of the form of two characters succeeded by five digits.

Thus, we can set up a mask in hashcat that reflects these criteria like so: “?u?u?d?d?d?d?d”. Also, we can tell by the size (128bits), that it is most likely an MD5 hash, and we feed that to our command with the -m 0 parameter.  Finally, we will use this mask in a brute force attack (-a 3 parameter). 

The final command we use looks like this: “hashcat -a 3 hash.txt ?u?u?d?d?d?d?d -m 0”. The attack is successful and the password from which the hash was created is the flag to this task: “PH76513”.

## 🧩 Lessons Learned
Knowledge of password format drastically reduces search space.

## 🧠 Tags
'#HashCracking' '#MD5' '#CTF' '#HashCat'

