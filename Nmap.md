## TCP (-sT) - Complete TCP Scan

![image](https://user-images.githubusercontent.com/34310266/169390619-0668d069-5be1-420a-a9f0-b7b20b573076.png)

This scan establish three-way handsharke and then send RST/ACK-packet to target
Advantage:
1) Results are highly accurate.
2) Handshake is complete, that ensures secure communication.
Disadvantage:
1) Very noisy, easy to detect
### Example for open port
>sudo nmap -sT -T2 -p 22  192.168.1.4

![image](https://user-images.githubusercontent.com/34310266/169389899-49f41152-2227-4f78-9394-66382769e25d.png)
![image](https://user-images.githubusercontent.com/34310266/169390032-7e591a43-7abb-4421-9146-4a424f462b8d.png)

### Example for Closed port

![image](https://user-images.githubusercontent.com/34310266/169390919-babd3e5b-0541-4b38-9551-b11cec27533f.png)

## Stealth Scan (-sS) - Half-open TCP Connection
SYN scan is the default and most  popular scan option for good reasons. It can be performed quickly,  scanning thousands of ports per second on a fast network not hampered by  restrictive firewalls. It is also relatively typical and stealthy since  it never completes TCP connections.

### Example for open port
> nmap -sS -p 22 -T2 192.168.1.4
> 
![image](https://user-images.githubusercontent.com/34310266/169657471-15b758ce-17d9-4d24-bbc1-bea1a7af680d.png)
![image](https://user-images.githubusercontent.com/34310266/169657853-00521fb4-2583-4932-9e6b-c228afc453f7.png)

### For Closed Ports

![image](https://user-images.githubusercontent.com/34310266/169657870-c9e8aa70-04c6-4eab-9df6-77bb6beda7a8.png)

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
