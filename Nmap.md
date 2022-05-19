## TCP (-sT) - Complete TCP Scan

![image](https://user-images.githubusercontent.com/34310266/169390619-0668d069-5be1-420a-a9f0-b7b20b573076.png)

This scan establish three-way handsharke and then send RST/ACK-packet to target
Advantage:
1) Results are highly accurate.
2) Handshake is complete, that ensures secure communication.
Disadvantage:
1) Very noisy, easy to detect
### Example for open port

![image](https://user-images.githubusercontent.com/34310266/169389899-49f41152-2227-4f78-9394-66382769e25d.png)
![image](https://user-images.githubusercontent.com/34310266/169390032-7e591a43-7abb-4421-9146-4a424f462b8d.png)

### Example for Closed port

![image](https://user-images.githubusercontent.com/34310266/169390919-babd3e5b-0541-4b38-9551-b11cec27533f.png)


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
