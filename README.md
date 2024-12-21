<h1>Network Share Drive Creation and Automated Backup</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Project Overview</h2>
This project focuses on creating a centralized network drive on a domain-connected server to serve as a structured file storage solution. Tasks include provisioning the drive, configuring shadow copy for backup and recovery, and organizing folders for each department within the company. This foundational setup ensures efficient data storage, future scalability, and preparation for implementing sharing permissions and access control.
<br />


<h2>Tools and Utilities Used</h2>

- <b>Virtual Box</b>
- <b>Windows Server</b>
- <b>Disk Management</b>
- <b>Server Manager - Files and Storage Services</b>

<h2>Setup & Configuration</h2>

- <b>Windows Server 2019</b></br>
  Shared Network Drive (S: Volume)</br>
  Shadow Copy Backup (B: Volume)</br>

<h2>Project Walkthrough</h2>

Currently the Windows Server does not have a drive that is set-up to be utilized across the Domain for different departments. This is what the storage environment looks like at present.
We'll want to create a new Volume from existing, unused, drive space.
<img src="https://i.imgur.com/5HYlOCe.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<br />
<br />
- <b>ACTION:</b> Shrunk the C: Volume to create Unallocated Space for our new Drive <br/>
<img src="https://i.imgur.com/8cPPGMs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/4i6tMEU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now that we have Disk space carved out for a Shared Network Drive, we can create the drive. We only use half the space available. This is important because we'll use the rest of the space later on when we configure automated backups.
- <b>ACTION:</b> Create the New Volume, give it a Drive Letter and Volume Label <br/>
<img src="https://i.imgur.com/FnlKYTb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0zDPjeG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Sc6ycl4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
We can see that our new drive is now present along with our other drives.
<img src="https://i.imgur.com/fNc7q2q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Our new drive is now populated into Server Manager. We'll use Server Manager to share the newly created drive across the domain using SMB because we're operating with Windows machines<br/>
<img src="https://i.imgur.com/Oj5TQqA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Ch8zcHU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/UJUvJxW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/njQBcdI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/T6Hwj3T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
We have to make sure that Administrators have access to this drive so we can set permissions for the OUs later on.
<img src="https://i.imgur.com/Pb65XCF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br /> 
- <b>ACTION:</b> Populated the Share Drive with the appropriate OUs to share later <br/>
<img src="https://i.imgur.com/JIF5or6.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<br />
<br />
- <b>ACTION:</b>Used Shadow Copy to create automated back-ups for the entire S: Volume. This Shadow Copy (B:) is the exact same size as the S: Volume so we can have there be no-limit to size.
- Also, we scheduled back-ups to be created every-day during off hours (2:00AM) so as not to interrupt the flow of a work-day. <br/>
<img src="https://i.imgur.com/OhJe3vQ.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<img src="https://i.imgur.com/WxU8u9v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/CLM87Xh.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<img src="https://i.imgur.com/WNnsQTF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/sGu1nE0.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<img src="https://i.imgur.com/Y3RmoqH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/jerv8ML.png" height="80%" width="80%" alt="VM and Server 2016 Steps"/>
<img src="https://i.imgur.com/6kS0cMm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/oT2zNHV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<h2>Conclusion and Key Learnings</h2>
Completing this lab provided valuable experience in setting up and managing a network drive within a domain environment. Key skills gained include drive provisioning, folder organization for departmental use, and configuring Shadow Copy for automated backups and version control. Utilities like Disk Management, Shadow Copy tools, and Windows Explorer were used to perform these tasks efficiently. This lab demonstrated the importance of planning storage architecture for scalability and backup reliability, laying the groundwork for implementing secure access permissions in the future.
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
