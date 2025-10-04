# OSINT Challenge — "Dark Energy"

Have you already checked padawan ports? There is a flag to be found on tcp/502.

## 🧰 Methodology
We begin by running a port scan on port 502 of the padawan.hackingarena.com domain (nmap -sT padawan.hackingarena.com -p502 -Pn). We see then that the service which is being run on this port is mbap (Modbus Application Protocol). We can attempt to act as a client (master) and query the server (slave) so as to figure out its input registers. We do so by using a tool called modpoll. The command we will use is “modpoll -c 125 158.37.63.170”, where -c specifies the number of values to read (1 – 125). The returned decimal values in ASCII reveal the flag. We can translate them ourselves using the ASCII table or use an ASCII to Text translator. By translating these values we figure out the flag: “HackingA{H4ck_the_bu5_4nd_n0_4l4ctricity}”.

## 🧩 Lessons Learned
Industrial protocols sometimes expose readable registers; careful decoding yields artifacts/flags.

## 🧠 Tags
'#modbus' '#nmap' '#Recon' '#Mapping'

