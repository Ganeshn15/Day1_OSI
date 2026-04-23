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

DNS
forward lookup zone: translates domain name to ip
reverse lookup zone:ip to domain name
Authoritative DNS zone:this zone has final authority over a query without asking other sources
Non-Authoritative DNS zone: information obtained from other sources like authoritative zones and cached the info for later use
primary zone: its a file where actual dns records are saved and managed; All the records can be changed here
Secondary zone: file acts as a read-only of primary zone;acts as a backup and improves response time for clients
DNSSEC,DNS OVER HTTPS(DoH), DNS OVER TLS(DoT)
