# Day1_OSI
 Appilcation layer --> Presentation layer --> Session layer --> Transport layer --> Network layer --> Datalink layer --> Physical layer
 uses protocols such   compressing/encrypting/ create-maintain-  TCP/UDP protocols   IP Address        MAC Address       data converted into bits
 as https/ftp/smtp     formatting data         end session         sequencing data    (packets)        (frames)                                      
         
 **COMMON PORTS**
HTTP(80) used to request webpages but it's not secure
HTTPS(443) does exactly as http but in a secured way
DNS(53) translates domain names to IP address
SMTP(25) is used to transfer emails
FTP(20/21) is used to send files accross a network. 21 is for commands & 20 through which transfer happens but not encrypted
SFTP/SSH(22) files are transfered accross a network in secure fashion/ Used for configuring and managing servers using command line
SMB(445) files are shared within LAN
TFTP(69) is utilized when configuration files or BIOS files need to be shared, not encrypted
NTP(123) synchronizes the time of all the devices in a network
SNMP(161/162) is a central management from which all the devices in a network are managed 
LDAP(389) uses active directory to access & manage the users and user objects
LDAPS (636)
SysLog(514) tracks all the event messages from the devices in a network which helps in understanding the status of the devices
# Day2_DNS
DHCP: dynamically/automatically assigns an ip address to a device when joined in a network
along with ip, it also assigns dns server,subnet maskand gateway address
few terms before configuring DHCP server
1. DHCP Scope: range of ip addresses need to be assigned in a network
2. Lease time/duration: time given to a device before deassigning an ip address
3. reservation: a particular address is dedicated to a dive with specific MAC address everytime it joins the network
4.Relay: DHCP provides or assignes ip addresses to different network within a subnet mask
DNS resolution chain: query from browser--> cache--> hostfile --> resolver(like ISP DNS first checks cache;if NOT then)--> ROOT server--> TLD server--> authoritative name server--> gives the address and sent back to client

DNS
forward lookup zone: translates domain name to ip
reverse lookup zone:ip to domain name
Authoritative DNS zone:this zone has final authority over a query without asking other sources
Non-Authoritative DNS zone: information obtained from other sources like authoritative zones and cached the info for later use
primary zone: its a file where actual dns records are saved and managed; All the records can be changed here
Secondary zone: file acts as a read-only of primary zone;acts as a backup and improves response time for clients
DNSSEC,DNS OVER HTTPS(DoH), DNS OVER TLS(DoT)
# Day3_linux
SSH is used to securely login/access the computer remotely
basic commands:
ls-lists all the files
cat-opens a file
du-gives disk usage of a file
du filename
find- helps to find/filter out the files or directories based on filetype, size, modified time, permissions etc
file- gives the type of file(not only the extension)
file filename
**dashed filenames:**
ex:"-sample.txt"
use delimiter in this case; anything followed by "--" is considered as filename
ex: cat -- -sample.txt(to open -sample.txt)
use ./ followed by filename to tell terminal that dashed filename is in current directory
use \ to make terminal skip considering the space
**Hidden file:** filename starting with period(.) are considered as hidden file
use -a to list all the files including hidden files
-la to list all files including permissions
-A to list all files along with hidden files excluding (.)&(..) files
filtering the files based on filetype and size
find . -type f -size xxxc
. speacifies find from current directory
f is a file d is directory
xxx is filesize
# Day4_Eventid
event ids(can be accessed by event viewer)
4624-successful login
4625-failed login
4672-admin login
4720-new user created
4726-user deleted
4725-user disabled
event id- tells what type event occurred
event logon type-tells how it happened
logon types: type2-interactive i.e, logged in person
type3- access over the network
file share access
type8- plaintext
type9-logged in using new credentials
type10-remote logins
type11- cached logins(offline)

core methods of powershell analysis:
1. Get-EventLog: pulls the event logs based on event ids and other filters
2. Get-WinEvent: same as Get-EventLog but more robust
3. Where-Object: filters result by specifying objects such as admin
4. Select-Object: gives only selected fields in output
