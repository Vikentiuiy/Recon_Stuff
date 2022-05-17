# Recon_Stuff
Tools and notes to work on reconnaissance stage more effectively
## Passive reconnaissance
### Search Engines (Dorks)
> You can use google, bing and other search engines to extract information such as username, password, hidden web pages, technology, the file contains metadata.
* [Exploit-DB](https://www.exploit-db.com/google-hacking-database)
* [Google Search Operators](https://www.indeed.com/career-advice/finding-a-job/google-search-operators)
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
### Reverse Whois 
* [ViewDNS](https://viewdns.info/reversewhois/)
* [Domaineye](https://domaineye.com/reverse-whois)
* [Reversewhois](https://www.reversewhois.io/)
### Useful Browser Addons (Mozilla)
* [Wappalyzer - Identify technologies on websites](https://addons.mozilla.org/en-US/firefox/addon/wappalyzer/)
* [Flagfox - Multitude of tools such as site safety checks, whois, translation](https://addons.mozilla.org/en-US/firefox/addon/flagfox/)
## Active reconnaissance
### Nmap
> Default command (-sC is for top nmap scripts, -sV for enum version, -oA to output result in file)
````
nmap -sC -sV -oA output 123.123.123.123
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
