# Wireshark Packet Capture Lab – Home Lab

<br>

<h2>Description</h2>
This project demonstrates network protocol analysis and troubleshooting in a Windows domain home lab using Wireshark.  
The lab focuses on Kerberos authentication, SMB file access, and ICMP connectivity testing.


<h2>Languages and Utilities Used</h2>

- <b>Virtual Box</b> 

<h2>Environments Used </h2>

- <b>Windows 2019 Server</b>
- <b>Windows 10 Pro (Client)</b>
- <b>Windows 10 Pro (Wireshark)</b>


## 1️⃣ Kerberos Authentication Error and Resolution

**Goal:**  
Analyze Kerberos authentication traffic between a domain client and Domain Controller to identify and resolve a KRB-ERROR observed during client login.

**What I Did:**  
- Captured authentication traffic using Wireshark while logging into a domain client VM.  
- Identified key Kerberos messages: AS-REQ, AS-REP, TGS-REQ, TGS-REP.  
- Observed a KRB-ERROR caused by a time synchronization issue between the client and Domain Controller.  
- Corrected the issue by configuring the Windows Time service and verified successful Kerberos authentication afterward.

**Outcome:**  
- Kerberos tickets (krbtgt and LDAP service tickets) were successfully issued.  
- Client authentication to the domain worked without errors.

**Key Skills Demonstrated:**  
Kerberos protocol analysis, Active Directory troubleshooting, Windows Time service configuration, Wireshark filtering, authentication error resolution.


<br>

![KRB Error](https://github.com/user-attachments/assets/632173a1-569b-4641-9914-e82e27dde094)
<br>

<br>


![Time Correction](https://github.com/user-attachments/assets/99bf62c4-4259-4dda-ac1c-82cfa878c063)



<br>





![WS KERB AUTH](https://github.com/user-attachments/assets/fcdcc3cd-7bec-4138-8bbc-42a5ed2a5c13)





<br>
<br>


## 2️⃣ SMB File Access and Shared Drive Traffic

**Goal:**  
Capture and analyze SMB traffic generated when a domain client accesses a shared folder on the Domain Controller and performs file operations.

**What I Did:**  
- Mapped a network drive from the client VM to a shared folder on the DC.  
- Captured packets while creating, editing, and deleting a test file.  
- Identified SMB operations: Tree Connect, Create Request, Write Request, Close Request.  
- Observed Kerberos tickets being used for SMB session setup.

**Outcome:**  
- Verified secure file operations using SMBv2 over Kerberos authentication.  
- Learned how layered protocols interact (Kerberos + SMB) in Windows domains.

**Key Skills Demonstrated:**  
SMB protocol analysis, secure session establishment, understanding layered protocol dependencies, network packet interpretation.




<br>

![networkdrive verification](https://github.com/user-attachments/assets/5089370b-2761-4531-9af1-476d47b8ddb0)

<br>



![filepackcap1](https://github.com/user-attachments/assets/1559e5fd-6419-4e74-ad87-ad301d59f1e6)



<br>




![filepackcap2](https://github.com/user-attachments/assets/7bfa41d4-389b-4952-9290-335a58f2d85b)


<br>


![kerberosticketsmb](https://github.com/user-attachments/assets/ad45cd84-a53a-4747-a8c6-ca9543171fc0)

<br>



## 3️⃣ ICMP Traffic and Firewall Connectivity Testing

**Goal:**  
Investigate network connectivity issues between a client and another VM, focusing on how Windows Firewall affects ICMP traffic.

**What I Did:**  
- Attempted to ping the Wireshark VM from the domain client; initial requests failed.  
- Captured packets in Wireshark showing Echo Requests without replies.  
- Temporarily disabled Windows Firewall and confirmed successful ICMP packet exchange.  
- Re-enabled firewall and configured an ICMP allow rule for controlled testing.

**Outcome:**  
- Resolved connectivity issues caused by firewall filtering.  
- Observed ICMP traffic flow under different firewall configurations.

**Key Skills Demonstrated:**  
Network troubleshooting, Windows Firewall configuration, ICMP protocol analysis, understanding security implications of inbound traffic filtering.




<br>

![pingrequesttimeout](https://github.com/user-attachments/assets/42eeeaac-9941-4223-a3cd-b5c9cfeddd07)

<br>


![pingnoreply](https://github.com/user-attachments/assets/fb4a38e1-5a59-40eb-b6b3-473d7db08111)




<br>


![firewall config](https://github.com/user-attachments/assets/0d5b7a99-5613-4379-802f-2e226798eb9f)



<br>

![pingreply](https://github.com/user-attachments/assets/c31c86c6-a511-42e8-b1db-395b9ee6d992)



## Conclusion

This lab demonstrates real-world network troubleshooting and protocol analysis using Wireshark.  
By capturing and interpreting Kerberos, SMB, and ICMP traffic, I gained hands-on experience with authentication, file access, and connectivity troubleshooting in a Windows domain environment.

<br>

