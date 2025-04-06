Challenge 1:
You are assigned a task to crack the NTLM password hashes captured by the internal security team. The password hash has been stored in the Documents folder of the Parrot Security console machine. What is the password of user James? (Format: aaaaaa)
use crackstation.com | john --format=nt hashes.txt


Challenge 2:
You are assigned a task to crack the NTLM password hashes captured by the internal security team. The password hash has been stored in the Documents folder of the Parrot Security console machine. What is the password of user Jones? (Format: NNNNNNNN)
use crackstation.com | john --format=nt hashes.txt


Challenge 3:
You have been given a task to audit the passwords of a server present in CEHORG network. Find out the password of the user Adam and submit it. (Note: Use Administrator/ CSCPass when asked for credentials). (Format: aaaaaaaaN)
use L0ptcrack in windows with given credentials
host is 10.10.10.25



Challenge 4:
An employee in your organization is suspected of sending important information to an accomplice outside the organization. The incident response team has intercepted some files from the employee's system that they believe have hidden information. You are asked to investigate a file named Confidential.txt and extract hidden information. Find out the information hidden in the file. Note: The Confidential.txt file is located at C:\Users\Admin\Documents in EH Workstation – 2 machine. (Format: Aaaaa/AaaaaaaNNNNN)
Use snow tool
put snow.exe and hidden file in same folder
open cmd and type snow.exe -C filename.txt


Challenge 5:
The incident response team has intercepted an image file from a communication that is supposed to have just text. You are asked to investigate the file and check if it contains any hidden information. Find out the information hidden in the file. Note: The vacation.bmp file is located at C:\Users\Admin\Documents in EH Workstation – 2 machine. (Format: AAANNNNNNN)
Use OpenStego
Select hidden file and click extract


Challenge 6:
A disgruntled employee in CEHORG has used the Covert_TCP utility to share a secret message with another user in the CEHORG network. Covert_TCP manipulates the TCP/IP header of the data packets to send a file one byte at a time from any host to a destination. It can be used to hide the data inside IP header fields. The employee used the IP ID field to hide the message. The network capture file “Capture.pcapng” has been retained in the “C:\Users\Administrator\Documents” directory of the “EH Workstation – 2” machine. Analyze the session to get the message that was transmitted. (Format: AN*A*AN)
Open that file in wireshark
filter with tcp && ip.addr = = 172.16.0.0/24 (CEHORG Network)
Note the first character in Differetiated service field -> identification for 10.10.1.10 to 172.16.0.11


Challenge 7:
You are a malware analyst working for CEHORG. During your assessment within your organisation's network, you found a malware face.exe. The malware is extracted and placed at C:\Users\Admin\Documents in the EH Workstation – 2 machine. Analyze the malware and find out the File pos for KERNEL32.dll text. (Hint: exclude zeros.) (Format: AANN)
Use Bintext (String searching tool)
search kernel32.dll  (use both small and cap letters)
first search not match search until match


Challenge 8:
Analyze an ELF executable (Sample-ELF) file placed at C:\Users\Admin\Documents in the EH Workstation – 2 machines to determine the CPU Architecture it was built for. (Format: AAAAANN)
open tool Ghidra
Just import file and refer the results window | Open parrot terminal and type file Sample.elf


Challenge 9:
CEHORG has assigned you with analysing the snapshot of the operating system registry and perform the further steps as part of dynamic analysis and find out the whether the driver packages registry is changed. Give your response as Yes/No. (Format: Aaa)
Use Reg Organizer and take the registry snapshot
Then run face.exe
Now compare the old screenshot with current registry
See differece in Driver under HKEY_Local_Machine 


Challenge 10:
Perform windows service monitoring and find out the service type associated with display name "afunix". (Format: aaaaaa)
Use servmon tool from ceh tools  | type sc qc afunix in cmd promt


Challenge 11:
Use Yersinia on the “EH Workstation – 1” (Parrot Security) machine to perform the DHCP starvation attack. Analyze the network traffic generated during the attack and find the Transaction ID of the DHCP Discover packets. (Format: NaNNNaNNNN)
Start wireshark and capture eth0
1. yersinia -G 
2. Click "Launch attack".
3. Click "DHCP".
4. Tick "sending DISCOVER packet".
5. Click "OK".
6. -> Click "Exit" to stop the attack
Goto wireshark and see Transaction id


Challenge 12:
CEHORG suspects a possible sniffing attack on a machine in its network. The organization has retained the network traffic data for the session and stored it in the Documents folder in EH Workstation – 2 (Windows 11) machine as sniffsession.pcap. You have been assigned a task to analyze and find out the protocol used for sniffing on its network. (Format: AAA)
open file with wireshark, Go to edit preferences - protocal - ARP/RARP - check Detect arp request stroms and detect duplicate ip and click ok.
You need to check all protocals for possible sniffing pattern, here filter Arp protocal , our preferences shows whether there is a duplicate use of ip or not


Challenge 13:
As an ethical hacker, you are tasked to analyze the traffic capture file webtraffic.pcapng. Find out the packet's id that uses ICMP protocol to communicate. Note: The webtraffic.pcapng file is located at C:\Users\Administrator\Documents\ in the Documents folder on EH Workstation – 2 (Windows 11) machine. (Format: NaaaNN)
Open the file in wire shark and filter icmp
you will see id in info of all packets


Challenge 14:
CEHORG has found that one of its web application movies.cehorg.com running on its network is leaking credentials in plain text. You have been assigned a task of analysing the movies.pcap file and find out the leaked credentials. Note: The movies.pcapng file is located at C:\Users\Administrator\Documents\ in the Documents folder on EH Workstation – 2 (Windows 11) machine. Make a note of the credentials obtained in this flag, it will be used in the Part 3 of CEH Skill Check. (Format: Aaaaa/aaaaaaa)
you know the ip of movies.cehorg.com, either filter with ip or http.request.method == POST
you will see the post form request, explore it for leaking credentials


Challenge 15:
An attacker has created a custom UDP packet and sent it to one of the machines in the CEHORG. You have been given a task to study the ""CustomUDP.pcapng"" file and find the data size of the UDP packet (in bytes). Note: The CustomUDP.pcapng file is located at C:\Users\Administrator\Documents\ in the Documents folder on EH Workstation – 2 (Windows 11) machine. (Format: NNN)
Filter udp and check for data of all packets, it shows the size of the data and don't consider the length because it shows the total packet size, we need only  data size


Challenge 16:
A denial-of-service attack has been launched on a target machine in the CEHORG network. A network session file "DoS.pcapng" has been captured and stored in the Documents folder of the EH Workstation - 2 machine. Find the IP address of the attacker's machine. (Format: NNN.NNN.N.NN)
Filter for tcp.flags.syn == 1 and tcp.flags.ack == 0     | Analyze -> Expertinformation (This frame undergoes the connection closing)


Challenge 17:
CEHORG hosts a datacenter for its bussiness clients. While analyzing the network traffic it was observed that there was a huge surge of incoming traffic from multiple sources. You are given a task to analyze and study the DDoS.pcap file. The captured network session (DDoS.pcapng) is stored in the Documents folder of the EH Workstation -2 machine. Determine the number of machines that were used to initiate the attack. (Format: N)
open wireshark, Go to statistics - conversations - IPv4 and count ip  or count highlighted ips in redcolor manually | tcp.analysis.retransmission







 