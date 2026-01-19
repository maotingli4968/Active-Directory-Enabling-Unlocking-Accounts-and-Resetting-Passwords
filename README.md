<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory – Enabling, Unlocking Accounts, and Resetting Passwords</h1>
This tutorial shows how to handle account lockouts and password resets in active directory.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- Active Directory Domain Services (AD DS)
- Group Policy Management Console (GPMC)


<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter (Domain Controller – DC-1)
- Windows 10 Pro (Client – Client-1)


<h2>List of Prerequisites</h2>

- Ensure that both <b>DC-1</b> and <b>Client-1</b> are powered on in the Azure Portal.
- You must have already deployed and configured these machines in earlier labs, with <b>DC-1</b> functioning as the <b>Domain Controller</b>.
- You should have previously created several <b>domain user accounts</b> that will be used in this exercise.



<h2>Simulate Account Lockout</h2>

- Log into <b>DC-1</b>.
- Choose one of the random domain user accounts you created earlier.
- From the client side, attempt to log in with this user account <b>10 times</b> using an incorrect password.
- This simulates repeated login failures that would normally trigger an <b>account lockout</b> in a production environment.

  <img width="975" height="1006" alt="image" src="https://github.com/user-attachments/assets/479bbc26-b4e9-4874-836b-9f68f21a19c3" />


  <h2>Configure Account Lockout Policy via Group Policy</h2>

- Open the <b>Group Policy Management Console</b> on <b>DC-1</b>.
- Create or edit a <b>Group Policy Object (GPO)</b> to enforce account lockouts.
- Set the <b>Account Lockout Threshold</b> to <b>5 failed attempts</b>.
- This ensures that after five incorrect password entries, the account will automatically lock.
- Apply the GPO so it propagates across the domain.

  <img width="975" height="709" alt="image" src="https://github.com/user-attachments/assets/2597ca95-4137-42c0-8d1f-b137228ae301" />

  



















<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
