# A-Beginner-s-Guide-to-Nmap

This github repo is made for all, ranging from beginners in cybersecurity to cybersecurity experts. This is a beginners friendly, so don't worry and enjoy reading.


## Introduction to Nmap

Nmap, short for Network Mapper, is a open source tool which is used to scan ip addresses and 
ports of a machine or on a network.

Nmap can be used for the following purposes -
- creating a complete network Map
- detecting open ports on local and remote systems
- getting os system and software details
- finding vulnerabilities on local and remote hosts
- detecting installed applications on a host

Now let's understand about different commands of nmap.

Ping Command –used to test the reachability of a host on an Internet (Checking whether the system is online or not).

For example -
```bash
  ping google.com
```
or 
```bash
  ping 8.8.8.8
```

Scan Command - used to find open and closed ports and the service running on that port on local and remote systems

```bash
  nmap google.com
```
Note -

1.	Add -v after nmap if you want to view the details while scan is running or wait for the scan to complete.

2.	If you want to change the dns service the nmap is using to find ip address by domain name, then use the below command.
nmap –dns-servers 1.1.1.1 mywebsite.com

3.	If you want to scan for a range of ports, then use the following command
nmap -p1-30 mywebsite.com

4.	If you want to scan for a particular port, then use the following command
nmap -p80 mywebsite.com

Version Detection Command - used for remote os Detection

```bash
  nmap -sV -v google.com
```

Aggressive Scan Command – used to enables OS detection, version detection, script scanning, and traceroute (Just insert -A in the command)

```bash
  nmap -A google.com
```
Note – 
1.	For indetifying live hosts on a local network, use the following command.
nmap.exe -sP defaultgateway/24

2.	For finding all live hosts on a local network, just simply enter netdiscover in a kali linux terminal.

3.	For scanning for multiple ports of your choice, use the following command
nmap -p80,443,23 mywebsite.com

Now let's see some cool examples of nmap -

To scan for port 80 on all local addresses run:
```bash
   nmap -p80 192.168.7.1/24 -v 
```
To scan port 80 on localhost run:
```bash
   nmap -p80 localhost -v
```
or
```bash
   nmap -p80 127.0.0.1
```
To scan multiple ports on one host run:
```bash
   nmap -p80,443,2000,4444 google.com
```
To scan a range of ports from 1 to 100 or any given range, run:
```bash
   nmap -p1-100 google.com
```
To scan for all available ports run:
```bash
   nmap -p- scanme.nmap.org
```
To scan for specific service, http for example run:
```bash
   nmap -p http localhost
```
or
```bash
   nmap -p http 127.0.0.1
```
To scan for all http related services run:
```bash
   nmap -p http* localhost
```
or
```bash
   nmap -p http* 127.0.0.1
```
To scan for https service run:
```bash
  nmap -p https localhost
```
To scan for all https related services run:
```bash
   nmap -p https* localhost
```

## Nmap Scripting Engine(NSE)

The Nmap Scripting Engine (NSE) is one of Nmap's most powerful and flexible features. It allows users to write (and share) simple scripts (using the Lua programming language ) to automate a wide variety of networking tasks. Those scripts are executed in parallel with the speed and efficiency you expect from Nmap.

- To begin with nse scripts run this example:

  nmap -sV --script http-title scanme.nmap.org

- to include multiple nse scripts in one scan:
  
  nmap -sV --script http-title,http-headers scanme.nmap.org

- to run all the scripts in NSE vulnerability category run:
  
  nmap --script vuln scanme.nmap.org

- to run all the scripts from multiple NSE categories run:
  
  nmap -sV --script="version,discovery" scanme.nmap.org

- to run all the scripts from exploit category run:
  
  nmap -sV --script exploit scanme.nmap.org

- to exclude specific nse category (in this case exploit category) run:
  
  nmap -sV --script "not exploit: scanme.nmap.org

- to exclude specific nse scripts (in this example we are excluding
  http-slowloris and http-brute) from nse category run:
  
  nmap -sV --script "(http-*) and not (http-slowloris or http-brute)" scanme.nmap.org

DNS Bruteforce Command - used to bruteforce dns record

```bash
   nmap --script dns-brute google.com
```

OS Identification Command - To find the details of OS
```bash
   nmap -O scanme.nmap.org -v
```

## FAQ

#### What are alternatives of Nmap ?

Their are a number of alternatives available on github today, but still nmap is the most popular and widely used.
Some of the famous ones are 

https://github.com/angryip/ipscan
https://github.com/robertdavidgraham/masscan

#### Is Nmap available in GUI?

Zenmap is the gui version of Nmap. Windows users can install that for the ease of use.

https://nmap.org/zenmap/


# Hi, I'm Dheeraj Yadav! 👋


## 🚀 About Me
I'm a 19y/o self-learned ethical hacker, mainly interested in bug hunting, malware analysis, and digital forensics. Currently expertise in SEO, OSINT, ethical hacking, WordPress, Shopify, front-end web.

## 🔗 Links
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dheerajydv19)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/dheerajydv19)


## Feedback

If you have any feedback, please reach out to me at any of the social media platform mentioned here.

 https://linktr.ee/dheerajydv19


## Support

For support, please star this repo and share it with others.


