# OSINT Challenge — "SQL Injection"

## 🧭 Executive Summary
Can you find the flag here: http://jabba.hackingarena.com:812

## 🧰 Methodology
The first step is to check if sql injection works on the page, so we try a simple script in the available form which will post all database contents without the need to match our keyword: “randomstring' or '1'='1'#”. It is confirmed that sql injection does work. The data we can extrapolate from such a simple page is limited, so we can try to take a look at the pre rendered php script of “index.php”. The way to do this is exploiting this sql injection vulnerability with a php filter to encode the script in base64:

“randomstring' union select 'php://filter/convert.base64-encode/resource=index.php'#”

Sure enough, we find the encoded script posted on the page so we can decode it for further hints using a base64 decoder. Throughout the script we notice the use of the php include statement which calls upon another php file. This hints at the existence of more than one php files we can possibly decode. By exfiltrating data from the database, we find out that there are three more php files which only contain one line and are not useful. But another possibility is the “connect.php” which contains the mysql configuration. We encode it by entering:

“randomstring' union select 'php://filter/convert.base64-encode/resource=connect.php'#”

and decode it with a base 64 decoder and indeed, in the decoded connect.php script we can see that the flag to this task is: “Hacking-Arena{Where_else_should_be_the_flag}”.


## 🧩 Lessons Learned
Blind/union SQLi can be combined with PHP filters to retrieve application files; always protect DB configs.

## 🧠 Tags
'#PHP' '#Exfiltration' '#Base64' '#SQLinjection'

