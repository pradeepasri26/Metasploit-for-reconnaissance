# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
## OUTPUT:

Find out the ip address of the attackers system
![322251458-e4eecafc-ea08-4bad-a5e7-e73bdf4f92c8](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/b0b8a202-ee86-4d10-96a1-1b04ece0c51a)
Invoke msfconsole: 
![322251470-13f4c2d0-33dc-4f7e-9b1a-20b0ea6a6d03](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/780cdef1-0e96-46fb-afde-801db21ca8c0)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![322251479-c7925edc-4906-4997-b313-3d4c17070396](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/c45b7245-4e8e-4ad7-b33d-04454c3fb9dc)
Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![322251484-f5c05b07-624a-4837-9467-f47f3b57cd06](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/98abccbb-8d3e-4abe-9953-912f4b7fa84c)
use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later. scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![322251506-d72934ca-83e0-40d8-98bc-5973033a772d](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/32b68ec1-cbfd-4970-a72a-0584ed8e272e)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![322251519-15df4ad0-59cb-4de1-88f9-0c23952c8469](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/6031a143-3186-422a-8944-e558165a9143)
![322251530-e1d02cf1-37dd-47d2-ac49-11bd1a653038](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/5f4cdb64-074e-4c2b-aed1-02363a4a7154)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![322251541-2993e57f-a594-4560-bb82-e86f110962b5](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/625540fe-68de-4134-a226-7d60b4620e88)
The info command provides information regarding a module or platform
![322251555-2af18165-2795-4a5a-ae5d-9c4c65c6fc2f](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/20135916-9f28-444e-a4b3-00317ebe105c)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![322251576-00182066-9c91-4bd8-ad63-7527d27e785b](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/c0d5f25c-59bc-45f2-b2d5-67cc9bf4f079)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![322251583-fda81f61-d4cc-47a9-a5ad-4ba08a7f3c15](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/5223d9c4-e60c-4137-97ed-dfa8fe7246a3)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![322251591-1f8a10c1-3b89-4482-95e6-6d762721d939](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/681c7860-1f02-4cf2-a396-aeeb21845c67)
Use the set rhosts command to set the parameter and run the module, as follows:
![322251601-60ca0e8e-fbd0-4e75-b0b5-0763ad26ddb1](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/66047689-af4c-45fd-b100-6caa4c04be5f)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![322251611-ed9f978e-5d23-4d4b-ade3-204de4fba1a9](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/69bd8611-6bf2-4421-a034-506560db5eb1)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![322251621-4cfd19a4-c8e3-438c-b272-9cbba0cf3caa](https://github.com/pradeepasri26/Metasploit-for-reconnaissance/assets/131433142/fff1565d-c74b-457d-957e-a1d5a62c81de)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
