
Challenge 1:
You are performing reconnaissance for CEHORG and has been assigned a task to find out the physical location of one of their webservers hosting www.certifiedhacker.com. What are the GEO Coordinates of the webserver? Note: Provide answer as Latitude, Longitude. (Format: NN.NNN, *NN.NNN)
cd Billciper
python billciper.py | https://hackertarget.com/geoip-ip-location-lookup/
3


Challenge 2:
Identify if the website www.certifiedhacker.com allows DNS zone transfer. (Yes/No) (Format: Aa)
use billciper option 7  | dig website axfr


Challenge 3:
Identify the number of live machines in 172.16.0.0/24 subnet. (Format: N)
nmap -sn 172.16.0.0/24
Don't consider ip ending with 0.1 as host


Challenge 4:
Find the IP address of the machine which has port 21 open. Note: Target network 172.16.0.0/24 (Format: NNN.NN.N.NN)
nmap -p 21 172.16.0.0/24 


Challenge 5:
Find the IP address of the Domain Controller machine in 10.10.10.0/24. (Format: NN.NN.NN.NN)
nmap -p 53 10.10.10.0/24


Challenge 6:
Perform a host discovery scanning and identify the NetBIOS name of the host at 10.10.10.25. (Format: AAAAAAAAA)
nmap -A 10.10.10.25


Challenge 7:
Perform an intense scan on 10.10.10.25 and find out the FQDN of the machine in the network. (Format: AaaaaAaaa.AAAAAA.aaa)
nmap -A 10.10.10.25


Challenge 8:
What is the DNS Computer Name of the Domain Controller? (Format: AaaaaAaaa.AAAAAA.aaa)
nmap -A 10.10.10.25


Challenge 9:
While performing a security assessment against the CEHORG network, you came to know that one machine in the network is running OpenSSH and is vulnerable. Identify the version of the OpenSSH running on the machine. Note: Target network 192.168.0.0/24. (Format: N.NaN)
nmap -p 22 192.168.0.0/24  -sV


Challenge 10:
During a security assessment, it was found that a server was hosting a website that was susceptible to blind SQL injection attacks. Further investigation revealed that the underlying database management system of the site was MySQL. Determine the machine OS that hosted the database. (Format: Aaaaaa)
check previous scan results or intense scan the ip with sql port open


Challenge 11:
Perform LDAP enumeration on the target network and find out how many user accounts are associated with the domain. (Format: N)
ldapsearch -h 10.10.10.25 -s base namingcontexts (To find domain name , use tis name to )
ldapsearch -x -h 10.10.10.25 -b "DC=CEHORG,DC=COM" "objectclass=user" cn       (or) enum4linux 10.10.10.25 | egrep "Account" (or) sudo nmap 10.10.10.25 --script=*user*


Challenge 12:
Perform an LDAP Search on the Domain Controller machine and find out the latest version of the LDAP protocol. (Format: AAAAaN)
ldapsearch -x -h 10.10.10.25


Challenge 13:
What is the IP address of the machine that has NFS service enabled? Note: Target network 192.168.0.0/24. (Format: NNN.NNN.N.NN)
nmap -p 2049 192.168.0.0/24 -open
Answer  : 192.168.0.51

Challenge 14:
Perform a DNS enumeration on www.certifiedhacker.com and find out the name servers used by the domain. (Format: aaN.aaaaaaaa.aaa, aaN.aaaaaaaa.aaa)
dnsenum website


Challenge 15:
Find the IP address of the machine running SMTP service on the 192.168.0.0/24 network. (Format: NNN.NNN.N.NN)
nmap -p 25 192.168.0.0/24 --open


Challenge 16:
Perform an SMB Enumeration on 192.168.0.51 and check whether the Message signing feature is enabled or disabled. Give your response as Yes/No. (Format: Aaa)
nmap -p 445 ip -sV -A
Answer: Yes

Challenge 17:
Perform a vulnerability research on CVE-2022-30171 and find out the base score and impact of the vulnerability. (Format: N.N Aaaaaa)
Go to https://nvd.nist.gov/


Challenge 18:
Perform vulnerability scanning for the domain controller using OpenVAS and identify the number of vulnerabilities with severity level as "medium". (Format: N)
run openvas
Refer the scanned results which is already done
Go to Scans -> Reports see the medium column 


Challenge 19:
Perform vulnerability scanning for the webserver hosting movies.cehorg.com using OpenVAS and identify the severity level of RPC vulnerability. (Format: N)
Go to Scans -> Results
Search for RPC in Filter box
see the row matches with rpc and movies.cehorg.com


Challenge 20:
Perform vulnerability scanning for the Linux host in the 172.16.0.0/24 network using OpenVAS and find the number of vulnerabilities with severity level as medium. (Format: N)
run openvas
Refer the scanned results which is already done
Go to Scans -> Reports see the medium column

