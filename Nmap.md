> TCP (-sT)
<img src="https://github.com/Vikentiuiy/Recon_Stuff/blob/main/Images/TCP_C.png">
````
sudo -sT - <IP>
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
