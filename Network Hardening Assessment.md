# OS Security Incident Report: Assessment

> OS Hardening

> Google Cybersecurity Professional Certificate

# Scenario

Review the following scenario. Then complete the step-by-step instructions.

You are a security analyst working for a social media organization. The organization recently experienced a major data breach, which compromised the safety of their customers’ personal information, such as names and addresses. Your organization wants to implement strong network hardening practices that can be performed consistently to prevent attacks and breaches in the future. 

After inspecting the organization’s network, you discover four major vulnerabilities. The four vulnerabilities are as follows:

    The organization’s employees' share passwords.

    The admin password for the database is set to the default.

    The firewalls do not have rules in place to filter traffic coming in and out of the network.

    Multifactor authentication (MFA) is not used. 

If no action is taken to address these vulnerabilities, the organization is at risk of experiencing another data breach or other attacks in the future. 

In this activity, you will write a security risk assessment to analyze the incident and explain what methods can be used to further secure the network.

## Response

### Part 1: Select up to three hardening tools and methods to implement

Password policies 
MFA (Multifactor Authentication)
Firewall maintenance 

### Part 2: Explain your recommendations

Implementing strong password policies aligned with current NIST guidelines, alongside multi-factor authentication (MFA), significantly reduces the risk of unauthorized access to sensitive data. NIST recommends using salting and hashing techniques to securely store passwords, which helps defend against brute-force attacks. Even if an attacker bypasses this layer, MFA provides an additional barrier by requiring access to a second factor, such as an authentication app or email account, which attackers are unlikely to possess.

MFA also discourages credential sharing among employees, as access requires the associated second factor. By following modern password policies that prioritize security without unnecessary complexity—thanks to salting and hashing—employees are less likely to forget their passwords, reducing the incentive to share them.

Regular firewall maintenance is equally important. Keeping firewalls updated ensures they can recognize and block newer types of threats before they reach critical internal networks or subnets, thereby enhancing the organization's overall security posture.
