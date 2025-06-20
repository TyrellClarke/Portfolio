# OS Security Incident Report: Assessment

> OS Hardening

> Google Cybersecurity Professional Certificate

# Scenario

You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A former employee has decided to lure users to a fake website with malware.

The former employee/ hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After embedding the malware, the hacker changed the password to the administrative account. When customers download the file, they are redirected to a fake version of the website that contains the malware.

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly. 
In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.
To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which contains the malware.  
The logs show the following process:
* The browser initiates a DNS request: It requests the IP address of the yummyrecipesforme.com URL from the DNS server.
* The DNS replies with the correct IP address. 
* The browser initiates an HTTP request: It requests the yummyrecipesforme.com webpage using the IP address sent by the DNS server.
* The browser initiates the download of the malware.
* The browser initiates a DNS request for greatrecipesforme.com.
* The DNS server responds with the IP address for greatrecipesforme.com.
* The browser initiates an HTTP request to the IP address for greatrecipesforme.com.

A senior analyst confirms that the website was compromised. The analyst checks the source code for the website. They notice that javascript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com. 
The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack. 
Your job is to document the incident in detail, including identifying the network protocols used to establish the connection between the user and the website.  You should also recommend a security action to take to prevent brute force attacks in the future.

## TCPdump Traffic Log

| Log Output |
| --- |
| 14:18:32.192571 IP your.machine.52444 > dns.google.domain: 35084+ A? yummyrecipesforme.com. (24)  |
| 14:18:32.204388 IP dns.google.domain > your.machine.52444: 35084 1/0/0 A203.0.113.22 (40)  |
| 14:18:36.786501 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [S], seq 2873951608, win 65495, options [mss 65495,sackOK,TS val 3302576859 ecr 0,nop,wscale 7], length 0 |
| 14:18:36.786517 IP yummyrecipesforme.com.http > your.machine.36086: Flags [S.], seq 3984334959, ack 2873951609, win 65483, options [mss 65495,sackOK,TS val 3302576859 ecr 3302576859,nop,wscale 7], length 0 |
| 14:18:36.786529 IP your.machine.36086 > yummyrecipesforme.com.http: Flags[.], ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 0 |
| 14:18:36.786589 IP your.machine.36086 > yummyrecipesforme.com.http: Flags [P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302576859 ecr3302576859], length 73: HTTP: GET / HTTP/1.1 |
| 14:18:36.786595 IP yummyrecipesforme.com.http > your.machine.36086: Flags[.], ack 74, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859], length 0 | <br>
| ...<a lot of traffic on the port 80>... |
| 14:20:32.192571 IP your.machine.52444 > dns.google.domain: 21899+ A?greatrecipesforme.com. (24) |
| 14:20:32.204388 IP dns.google.domain > your.machine.52444: 21899 1/0/0 A192.0.2.17 (40) |
| 14:25:29.576493 IP your.machine.56378 > greatrecipesforme.com.http: Flags[S], seq 1020702883, win 65495, options [mss 65495,sackOK,TS val 3302989649ecr 0,nop,wscale 7], length 0 |
| 14:25:29.576510 IP greatrecipesforme.com.http > your.machine.56378: Flags[S.], seq 1993648018, ack 1020702884, win 65483, options [mss 65495,sackOK,TSval 3302989649 ecr 3302989649,nop,wscale 7], length 0 |
| 14:25:29.576524 IP your.machine.56378 > greatrecipesforme.com.http: Flags[.], ack 1, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 0 |
| 14:25:29.576590 IP your.machine.56378 > greatrecipesforme.com.http: Flags[P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302989649 ecr3302989649], length 73: HTTP: GET / HTTP/1.1 |
| 14:25:29.576597 IP greatrecipesforme.com.http > your.machine.56378: Flags[.], ack 74, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649], length 0 | <br>
| ...<a lot of traffic on the port 80>... |

## Incident Report

### Section 1: Identify the network protocol involved in the incident 
 The network protocols involved in this incident are DNS and HTTP. DNS is used to resolve domain names into public IP addresses, and HTTP (via port 80) is used to handle communication between the client and the web server. Both protocols operate at the Application layer of the TCP/IP model. Additionally, TCP (at the Transport layer) is responsible for establishing and maintaining the connections. 

### Section 2: Document the incident 

 The issue was first reported when several customers contacted the company to report that the website had prompted them to download a file in order to access free recipes. After running the file, they noticed that the website address changed and their computers began running slowly.
Shortly after, the website owner attempted to log into the admin panel but was unable to access it, as the password had been changed without authorization.
The company’s security team responded by setting up a sandbox environment to safely observe the website's behavior. Using the network protocol analyzer tcpdump, they visited the suspicious URL — yummyrecipesforme.com — and were able to replicate the same behavior the users experienced. After executing the file, the browser redirected to a new domain: greatrecipesforme.com, where further malicious activity was detected.
Analysis of the captured traffic revealed the following sequence:
* A DNS request was made to resolve the IP address for yummyrecipesforme.com.
* The DNS server returned the correct IP address.
* An HTTP request was made to the website via port 80.
* The browser was prompted to download a suspicious file.
* After execution, a new DNS request was made for greatrecipesforme.com.
* The DNS response provided the IP for that domain.
* The browser was redirected to greatrecipesforme.com, where additional HTTP traffic was observed.

A senior analyst confirmed that the original website had been compromised. By reviewing the site’s source code, they found that malicious JavaScript had been injected. This code prompted users to download a file, which contained a script to redirect traffic to the spoofed domain.
It was ultimately determined that the attacker had gained access through a brute force attack, exploiting a weak admin password that had never been changed from its default setting. No security controls, such as account lockouts or rate-limiting, were in place to prevent repeated login attempts 

### Section 3: Recommend one remediation for brute force attacks
To help prevent this type of attack in the future, the company should implement a strong password policy and multi-factor authentication (MFA).
For example:
* Require passwords to be at least 8 characters long and include a mix of upper and lowercase letters, numbers, and symbols.
* Enforce regular password changes (e.g., every 90 days).
* Implement two-factor authentication (2FA), preferably using an authenticator app or email verification.
* Consider using one-time passwords (OTPs) for admin logins.
These measures significantly reduce the likelihood of a successful brute force attack and greatly improve the company’s overall security posture.
