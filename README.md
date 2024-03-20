Better version of Incursore. WIP. 
Changes:
Change #1: Cutycapt removal
Change #2: All scan will run everything (Type = All)


# Braqueur
```bash
    ____                                        
   / __ )_________ _____ ___  _____  __  _______
  / __  / ___/ __ `/ __ `/ / / / _ \/ / / / ___/
 / /_/ / /  / /_/ / /_/ / /_/ /  __/ /_/ / /    
/_____/_/   \__,_/\__, /\__,_/\___/\__,_/_/     
                    /_/
             @CinnamonBreadowo     
```
*Braqueur* will raid the target for you.

## TL;DR
"While *incursore* was born from *nmapAutomator*, it is **not** *nmapAutomator*. The script from @21y4d is great, but sometimes it's too slow (due to nikto). By removing it, the time needed to complete a scan has been drastically reduced.
So, from just removing nikto I found myself tweaking it a lot, that's why I decided to rename it to incursore and to publish it under a new repo and name."
-Wirzka

Braqueur, (French for raider/robber) has multiple changes to incursore. It has removed capycupt, automatically will run maximum recon, and (add more as more changes are made) 



## Features and changes
*Braqueur* has the following features (and more, of course):
- It immmediately runs a full TCP port scans
- It asks to the user to run with sudo in order to run a SYN Scan instead of a Connect Scan
- It automatically tries to bruteforce FTP services
- It runs *ffuf* instead of *gobuster*
- It does not run *nikto*
- It has not the remote capabilities

## Requirements
*Incursore*'s requirements are the following:
|      tool      |      scope      | official link |
|:--------------:|:---------------:|:-------------:|
|      nmap      |   recon/enum    | https://nmap.org/              |
|  nmap vulners  |      recon      |   https://github.com/vulnersCom/nmap-vulners            |
|      ffuf      |    web enum     |  https://github.com/ffuf/ffuf             |
|    sslscan     |    web enum     |  https://github.com/rbsec/sslscan             |
|    joomscan    |    web enum     | https://github.com/OWASP/joomscan              |
|     wpscan     |    web enum     |   https://github.com/wpscanteam/wpscan            |
|   droopescan   |    web enum     | https://github.com/droope/droopescan              |
|     smbmap     |    smb enum     | https://github.com/ShawnDEvans/smbmap              |
|   enum4linux   |    smb enum     |   https://github.com/CiscoCXSecurity/enum4linux            |
|   snmp-check   |    snmp enum    | https://www.nothink.org/codes/snmpcheck/index.php              |
|    snmpwalk    |    snmp enum    |https://linux.die.net/man/1/snmpwalk               |
|      odat      | oracle db recon |   https://github.com/quentinhardy/odat            |
|   ldapsearch   |    ldap enum    |   https://linux.die.net/man/1/ldapsearch            |
|    dnsrecon    |    dns enum     | https://github.com/darkoperator/dnsrecon              |
| smtp-user-enum |    smtp enum    | https://github.com/pentestmonkey/smtp-user-enum              |
|     hydra      | ftp bruteforce  | https://github.com/vanhauser-thc/thc-hydra              |


The majority of them is already present in pentesting distro like Parrot OS and Kali Linux.
To find out how many of them are missing on your machine, just launch a which command like this:
```bash
$ which nmap ffuf sslscan joomscan wpscan droopescan smbmap enum4linux snmp-check snmpwalk odat ldapsearch dnsrecon smtp-user-enum hydra
```

## Installation
```bash
git clone https://github.com/CinnamonBreadowo/braqueur.git
sudo ln -s $(pwd)/braqueur/braqueur.sh /usr/local/bin/
chmod +x $(pwd)/braqueur/braqueur.sh
cd $(pwd)/braqueur


```
## Usage
```bash
$ braqueur.sh -h
    ____                                        
   / __ )_________ _____ ___  _____  __  _______
  / __  / ___/ __ `/ __ `/ / / / _ \/ / / / ___/
 / /_/ / /  / /_/ / /_/ / /_/ /  __/ /_/ / /    
/_____/_/   \__,_/\__, /\__,_/\___/\__,_/_/     
                    /_/
             @CinnamonBreadowo                     

Usage: braqueur.sh -H <TARGET-IP> 
Optional: [-d/--dns <DNS SERVER>] [-o/--output <OUTPUT DIRECTORY>]

Scan Types:
        Port    : Shows all open ports
        Script  : Runs a script scan on found ports
        UDP     : Runs a UDP scan "requires sudo"
        Vulns   : Runs CVE scan and nmap Vulns scan on all found ports
        Recon   : Suggests recon commands, then prompts to automatically run them
        All     : Runs all the scans

inspired by @21y4d and @wirzka gently modified by @CinnamonBreadowo
```
## Future Features
- Generally increasing auto reconnaissance based on discovered services.

## Disclaimer
I am not responsible for any damages (tangible or intangible) resulting from the use of *braqueur*.
You must have the permissions to use it.

Stay safe.
