\# Day 1 – Identity Security Fundamentals



\## Project Overview



This project introduces the fundamentals of enterprise identity security and the role identity plays in modern cybersecurity.



Modern organisations rely heavily on cloud identity platforms such as Microsoft Entra ID to manage users, devices, applications, authentication, and access control.



The objective of this project is to understand how identity-based attacks occur and how security teams investigate suspicious authentication activity.



\---



\# Business Scenario



An organisation uses Microsoft Entra ID to manage employee identities and access to cloud resources.



Because user accounts provide access to business applications and data, compromised identities represent a significant security risk.



The security team needs to understand:



\- How users authenticate

\- How access is controlled

\- How suspicious sign-ins are detected

\- How identity incidents are investigated



\---



\# Security Problem



Identity-based attacks are one of the most common methods attackers use to gain initial access to organisations.



Examples include:



\- Phishing attacks

\- Password spraying

\- Credential theft

\- MFA fatigue attacks

\- Token theft



A compromised account can allow attackers to access business systems without immediately triggering traditional malware detection.



\---



\# Security Risk



A compromised identity could lead to:



\- Unauthorised access to company resources

\- Data theft

\- Business email compromise

\- Privilege escalation

\- Lateral movement

\- Financial fraud



Identity security controls are therefore a critical part of enterprise security.



\---



\# Objectives



The objectives of this project were to understand:



\- Authentication vs Authorization

\- Microsoft Entra ID fundamentals

\- Identity components

\- Common identity attack techniques

\- Sign-in log information used during investigations

\- The security investigation process for suspicious account activity



\---



\# Investigation / Research



The following areas were explored:



\## Authentication



Understanding how organisations verify user identity through:



\- Password authentication

\- Multi-factor authentication (MFA)

\- Passwordless authentication methods



\---



\## Authorization



Understanding how organisations control access after identity verification.



\- User permissions

\- Security groups

\- Role-based access control (RBAC)



\---



\## Microsoft Entra ID Components



Explored key identity components:



\- Users

\- Groups

\- Devices

\- Applications

\- Roles

\- Authentication methods



\---



\## Identity Attack Techniques



Reviewed common identity threats:



\### Password Spray



Attackers attempt a small number of commonly used passwords against many accounts.



\### Brute Force



Attackers attempt many passwords against a single account.



\### MFA Fatigue



Attackers repeatedly send MFA requests hoping a user approves one.



\### Token Theft



Attackers obtain authentication tokens to access resources without using a password.



\### Phishing



Attackers trick users into providing credentials through fake login pages.



\---



\# Tools Used



\- Microsoft Entra ID security concepts

\- Microsoft security documentation

\- GitHub for technical documentation and portfolio development



\---



\# Findings



Identity is a critical security layer because most enterprise resources depend on authenticated users.



Security teams rely on identity telemetry such as:



\- User activity

\- Sign-in location

\- IP address

\- Authentication method

\- Device information

\- Risk indicators



to identify potentially compromised accounts.



\---



\# Security Improvement



Improved understanding of:



\- How identity attacks occur

\- How authentication activity can be investigated

\- What evidence security analysts collect during identity investigations

\- How identity controls reduce security risk



\---



\# Business Impact



A strong identity security foundation helps organisations:



\- Reduce account compromise risk

\- Improve threat detection

\- Strengthen access control

\- Respond faster to suspicious activity



\---



\# Lessons Learned



Identity is one of the most important security domains in modern organisations.



Security analysts must understand:



\- Who accessed a system

\- What actions occurred

\- When activity happened

\- Where access originated

\- How attackers gained access

\- Why security controls failed



This investigation mindset is essential for incident response and threat hunting.



\---



\# Future Improvements



Future development areas:



\- Create a Microsoft Entra ID lab environment

\- Configure MFA controls

\- Implement Conditional Access policies

\- Explore Identity Protection

\- Investigate sign-in logs

\- Connect identity data to Microsoft Sentinel

\- Create KQL queries for identity threat detection

