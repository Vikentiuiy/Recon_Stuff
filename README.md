## Main Goal
Reconnaissance  consists of techniques that involve adversaries actively or passively  gathering information that can be used to support targeting. Such  information may include details of the victim organization,  infrastructure, or staff/personnel. This information can be leveraged by  the adversary to aid in other phases of the adversary lifecycle, such  as using gathered information to plan and execute Initial Access, to  scope and prioritize post-compromise objectives, or to drive and lead  further Reconnaissance efforts.

## Passive reconnaissance
### Search Engines (Dorks)
> You can use google, bing and other search engines to extract information such as username, password, hidden web pages, technology, the file contains metadata.
* [Exploit-DB](https://www.exploit-db.com/google-hacking-database)
* [Google Search Operators](https://www.indeed.com/career-advice/finding-a-job/google-search-operators)
* [Search Operators Cheatsheet](https://github.com/Vikentiuiy/Recon_Stuff/blob/main/google-search.png)
### Special Search engines (Shodan,Censys)
> Good choice to walk all over target external network resources if you don't want to scan resources yourself or if you're searching for a low hanging fruits
* [Shodan](https://www.shodan.io/)
* [Censys](https://censys.io/)
### DNS INFO
* Dnsrecon
````
dnsrecon -r <DNS Range> -n <IP_DNS>   #DNS reverse of all of the addresses
dnsrecon -d facebook.com -r 157.240.221.35/24 #Using facebooks dns
dnsrecon -r 157.240.221.35/24 -n 1.1.1.1 #Using cloudflares dns
dnsrecon -r 157.240.221.35/24 -n 8.8.8.8 #Using google dns
````
### Recon-ng
* [Good Tutorial](https://hackertarget.com/recon-ng-tutorial) 
### Github-CI/CD Flaws
* [Gitleaks](https://github.com/zricethezav/gitleaks)
### Reverse Whois 
* [ViewDNS](https://viewdns.info/reversewhois/)
* [Domaineye](https://domaineye.com/reverse-whois)
* [Reversewhois](https://www.reversewhois.io/)
### Useful Browser Addons (Mozilla)
* [Wappalyzer - Identify technologies on websites](https://addons.mozilla.org/en-US/firefox/addon/wappalyzer/)
* [Flagfox - Multitude of tools such as site safety checks, whois, translation](https://addons.mozilla.org/en-US/firefox/addon/flagfox/)
## Active reconnaissance
### Scapy
> Scapy is a Python program that enables the user to send, sniff and dissect and forge network packets. This capability allows construction of tools that can probe, scan or attack networks.
* [Documentation](https://scapy.readthedocs.io/en/latest/index.html)
### Nmap
> TCP 
````
sudo -sS -sC -sV -oA <NAME>.tcp <IP> -v
````
> UDP
````
sudo -sU -sS -sC -sV -oA <NAME>.udp <IP> -v
````
> LDAP
````
nmap -n -sV --script "ldap* and not brute"
````
> MSSQL
````
nmap --script ms-sql-info,ms-sql-empty-password,ms-sql-xp-cmdshell,ms-sql-config,ms-sql-ntlm-info,ms-sql-tables,ms-sql-hasdbaccess,ms-sql-dac,ms-sql-dump-hashes --script-args mssql.instance-port=1433,mssql.username=sa,mssql.password=,mssql.instance-name=MSSQLSERVER -sV -p 1433 <IP>
````
> NFS
````
nmap --script=nfs-showmount -oN mountable_shares <IP>
````
> VNC
````
nmap -sV --script vnc-info,realvnc-auth-bypass,vnc-title -v -p <PORT> <IP>
````
 > is an extended (all ports scan) option
 ````
 nmap -p-
 ````
 > Custom script usage
````
nmap --script =/your-scripts
````
### Dirbuster
* [Guide](https://www.hackingarticles.in/comprehensive-guide-on-dirbuster-tool/)
