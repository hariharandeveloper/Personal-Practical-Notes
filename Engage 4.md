Challenge 1:

The mobile device of an employee in CEHORG has been hacked by the hacker to perform DoS attack on one of the server in company network. You are assigned to analyse "Andro.pcapng" located in Documents directory of EH workstation-2 and identify the severity level of the attack. (Note: perform deep down Expert Info analysis). (Format: Aaaaaaa )
⦁	Open in wireshark, Goto Analyze -> Expert Information
⦁	View the Severity column


Challenge 2:

An ex-employee of CEHORG is suspected to be performing insider attack. You are assigned a task to attain KEYCODE-75 used in the employees' mobile phone. Note: use option p in PhoneSploit for next page. (Format: AAAAAAAAAA )
⦁	cd Phonesploit/
⦁	python3 phonesploitpro.py
⦁	p
⦁	24
⦁	View line no 75


Challenge 3:

An employee in CEHORG has secretly acquired Confidential access ID through an application from the company. He has saved this information on the Downloads folder of his Android mobile phone. You have been assigned a task as an ethical hacker to access the file and delete it covertly. Enter the account information present in the file. Note: Only provide the numeric values in the answer field. (Format: NNNNNNNN)
⦁	cd Phonesploit/
⦁	python3 phonesploitpro.py
⦁	9
⦁	172.16.0.21 (Found in 1st wireshark challenge)
⦁	/sdcard/Download
⦁	/home/attacker/Desktop
⦁	open Download folder in Desktop


Challenge 4:

An attacker has hacked one of the employees android device in CEHORG and initiated LOIC attack from the device. You are an ethical hacker who had obtained a screenshot of the attack using a background application. Obtain the screenshot of the attack using PhoneSploit from the attacked mobile device and determine the targeted machine IP along with send method. (Format: NNN.NN.N.NN/AAAA)
⦁	Use phonesploit shell or use adb shell
⦁	adb connect 172.16.0.21:5555
⦁	use cd command in adb shell to find any picture in sdcard folders
⦁	i found in /sdcard/DCIM
⦁	adb pull /sdcard/DCIM /home/attacker/Desktop
⦁	Open it for answer


Challenge 5:

An attacker installed a malicious mobile application 'AntiMalwarescanner.apk' on the victims android device which is located in EH workstation-2 documents folder. You are assigned a task to perform security audit on the mobile application and find out whether the application using permission to Read-call-logs. (Format: Aaa )
⦁	Goto sisik.eu/apk-tool
⦁	upload the given apk
⦁	see Permissions topic


Challenge 6:

CEHORG hosts multiple IOT devices and sensors to manage its supply chain fleet. You are assinged a task to examine the file "IOT Traffic.pcapng" located in the Home directory of the root user in the "EH Workstation - 1" machine. Analyze the packet and find the topic of the message sent to the sensor. (Format: Aaaaa*Aaaaa)
⦁	Open that file in wireshark
⦁	Filter for mqtt (protocal used by IOT) or  {mqtt and mqtt.msgtype == 3 }
⦁	Check for Publish Message packet
⦁	Expand the MQTT message to see the topic


Challenge 7:

CEHORG hosts multiple IOT devices and network sensors to manage its IT-department. You are assigned a task to examine the file "NetworkNS_Traffic.pcapng" located in the Documents folder of the user in the "EH Workstation - 2" machine. Analyze the packet and find the alert message sent to the sensor. (Format: Aaaa Aaa*aa *aaaa)
⦁	Open that file in wireshark
⦁	Filter for mqtt (protocal used by IOT)
⦁	Check for Publish Message packet
⦁	Expand the MQTT publish message to see the message


Challenge 8:

You have received a folder named "Archive" from a vendor. You suspect that someone might have tampered with the files during transmission. The Original hashes of the files have been sent by the sender separately and are stored in a file named FileHashes.txt stored in the Document folder in the "EH Workstation – 2" machine. Your task is to check the integrity of the files by comparing the MD5 hashes. Compare the hash values and determine the file name that has been tampered with. Note: Exclude the file extension in the answer field. The answer is case-sensitive. (Format: Aaaaaa)
⦁	Add the Archive filder to the MD5 calculator application
⦁	Compare with filehashes.txt


Challenge 9:

An attacker has intruded into the CEHORG network with malicious intent. He has identified a vulnerability in a machine. He has encoded the machine's IP address and left it in the database. While auditing the database, the encoded file was identified by the database admin. Decode the EncodedFile.txt file in the Document folder in the "EH Workstation – 2" machine and enter the IP address as the answer. (Hint: Password to decode the file is Passw0rd). (Format: NN.NN.NN.NN)
⦁	Decode that file with BCTextEncoder use (Passw0rd) as passphrase


Challenge 10:

The Access code of an employee was stolen from the CEHORG database. The attacker has encrypted the file using the Advance Encryption Package. You have been assigned a task to decrypt the file; the organization has retained the cipher file ""AccessCode.docx.aes"" in the Document folder in the ""EH Workstation – 2"" machine. Determine the access code by decrypting the file. Hint: Use ""qwerty"" as the decryption password. Note: Advanced Encryption Package is available at E:\CEH-Tools\CEHv12 Module 20 Cryptography\Cryptography Tools. (Format: AAA*AAA*NNNN)
⦁	Open that file in AES Tool, use (qwerty) as passphrase


Challenge 11:

A VeraCrypt volume file "secret" is stored on the Document folder in the "EH Workstation – 2" machine. You are an ethical hacker working with CEHORG; you have been tasked to decrypt the encrypted volume and determine the number of files stored in the volume. (Hint: Password: test). (Format: N)
⦁	Open file with VeraCrypt and use (test) as PassPhrase and choose free drive letter

Challenge 12:

An attacker had sent a file cryt-128-06encr.hex containing ransom file password, which is located in documents folder of EH-workstation-2. You are assigned a task to decrypt the file using cryp tool. Perform cryptanalysis, Identify the algorithm used for file encryption and hidden text. Note: check filename for key length and hex characters. (Format: Aaaaaaa/**aa**aA*a)
⦁	Open that file in Crypt tool and goto Encrypt/Decrypt
⦁	Try all the options in Symmentric list (First try modern)
⦁	Here Twofish
⦁	Choose 128 as key lenght
⦁	and 06 as hex key
⦁	Decrypt
