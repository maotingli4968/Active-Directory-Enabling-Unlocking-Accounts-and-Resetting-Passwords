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

  
<h2>Test Lockout Policy</h2>

- On <b>Client-1</b>, attempt to log into the same user account with a wrong password <b>six times</b>.
- You should observe that the account is now <b>locked</b>. This confirms that the Group Policy setting has taken effect.
- Back on <b>DC-1</b>, open <b>Active Directory Users and Computers (ADUC)</b> to view the account status and confirm that it is locked.

  <img width="975" height="268" alt="image" src="https://github.com/user-attachments/assets/9258418e-1364-45e3-b435-35ba9207934f" />

  <img width="630" height="822" alt="image" src="https://github.com/user-attachments/assets/fcc96237-4f5d-470b-8c0e-0899cc93232b" />


  <h2>Unlock and Reset the User Account</h2>

- From <b>DC-1</b>, unlock the account in <b>ADUC</b>.
- Reset the user’s password to a new one of your choice.
- Attempt to log back into <b>Client-1</b> with the updated credentials to confirm the account is functioning normally again.

  <img width="616" height="431" alt="image" src="https://github.com/user-attachments/assets/08c800fc-ef4e-4963-bb58-8fd22343bf34" />

  <img width="839" height="286" alt="image" src="https://github.com/user-attachments/assets/838719bb-c61b-4598-93ba-f7bbf52d2f2c" />



  <h2></h2> Enable and Disable Accounts</h2>

- Using the same test account, disable it in <b>ADUC</b> on <b>DC-1</b>.
- Attempt to log in from <b>Client-1</b> and observe the error message indicating the account has been disabled.
- Re-enable the account in <b>ADUC</b>, then try logging in again to confirm access is restored.

  Error message when logging in with disabled account.

  <img width="975" height="240" alt="image" src="https://github.com/user-attachments/assets/2b937a9c-8f9f-4add-989b-eb16f1c2ec09" />

   Re-enabled account working after login.

  <img width="864" height="311" alt="image" src="https://github.com/user-attachments/assets/e4fce23b-a370-46dd-ae59-bd60597d87c5" />


<h2></h2> Observe Security Logs</h2>

- Examine the security logs on both <b>DC-1</b> and <b>Client-1</b>.
- Look for entries that correspond to:
  - Failed login attempts
  - Account lockouts
  - Password resets
  - Account enabling/disabling

<img width="975" height="421" alt="image" src="https://github.com/user-attachments/assets/17f7d8c1-2221-4afa-bfc1-3a3888edf3db" />

























