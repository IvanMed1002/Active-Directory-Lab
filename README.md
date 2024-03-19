<h1>Active Directory (IAM)</h1>

<h2>Lab Objective</h2>

<br>Install Windows Server 2019 on the new virtual machine in VirtualBox and add the Active Directory Domain Services role to the server. Promote the server to a domain controller and create a new domain while also configuring DHCP. Use a PowerShell script to create over 1,000 users in Active Directory. Create a new virtual machine with Windows 10 and join it to the domain. Log in to the Windows 10 virtual machine with one of the newly created user accounts. <br />

<h2>Environments Used </h2>

- <b>VirtualBox installed on host machine<b/>
- <b>Microsoft Server 2019 ISO<b/>
- <b>Windows 10 Enterprise ISO<b/>

<h2>Project Walk-Through Overview </h2>

- <b>Set up Virtual Environment </b>

1. Download and install VirtualBox.<br/>
2. Download Microsoft Server 2019 iso from Microsoft.<br/>
3. Create new VM with Microsoft Server 2019 as OS.<br/>

 
<img src="https://i.imgur.com/FgaNsrh.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/xJt4oBT.png"/>

-----------------------------------------------

- <b>Setup Windows Server</b>

 1. Start the VM and follow the prompts to install Windows Server 2019.<br/>
 2. Install “Guest Additions” to enhance the overall usability of the VM and enable features like resizing the VM window and clipboard sharing between the host and guest operating systems.<br/>
 3. Set up the network adapters in VirtualBox and Windows Server.<br/>


 
<img src="https://i.imgur.com/fFOllVt.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/mALx3jn.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/uS5ghYi.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/xpTDfso.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/oE0cBJT.png"/>

-----------------------------------------------
 
<img src="https://i.imgur.com/piXXsCv.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/vD8WLFp.png"/>

-----------------------------------------------

- <b>Set up Active Directory Domain Services Role</b>

1. Login to Windows Server Vm as administrator and open "Server Manager" to "Add Roles and Features" <br/>

 
<img src="https://i.imgur.com/k4q9YXG.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/DVa0Zgx.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/DQtE10F.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/9zXA6vw.png"/>

-----------------------------------------------

2. Promote the Virtual Machine to a Domain Controller (this will manage network securities and allow users to authenticate and access network  resources).<br/>


<img src="https://i.imgur.com/ppe8ksN.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/IYHlCjP.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/eSZUEpe.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/GowC8UJ.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/cmzK4fj.png"/>

-----------------------------------------------

- <b>Create a dedicated domain administrator account and then give it admin privileges</b>

1. Open the Active Directory Users and Computers tool on your domain controller and create new organization unit named "_ADMINS_" and create user called "admin".<br/>
2. Add "admin" user to domain group to make user a member of "domain admins"<br/>

 
<img src="https://i.imgur.com/KpDSRsn.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/qDBOx81.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/d0udSlO.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/VUwhyF9.png"/>

-----------------------------------------------


- <b>Configure a Dynamic Host Configuration Protocol (DHCP)</b>

1. Install the DHCP server role in Server Manager (this will allow automatically assign IP addresses)<br/>
2. Create a new DHCP scope for IP address range and subnet mask.<br/>
3. Authorize the DHCP server to allow the DHCP server to provide IP addresses to devices on the network.<br/>


 
<img src="https://i.imgur.com/o5jZPEE.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/6zjUYSL.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/ojkV6n9.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/qCEWZfu.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/8kywnJj.png"/>

-----------------------------------------------

- <b>Run a PowerShell Script to Create Users in Active Directory</b>

1. Instead of manually creating each user, we’ll use a PowerShell script to create over 1000 users at once.<br/>
2. Enable “drag and drop” between your host and guest machine to allow script file to be downloaded from the host machine and transferred over to the VM machine.<br/>
3. Run script as Administrator in PowerShell ISE.<br/>

 
<img src="https://i.imgur.com/rfCpLFc.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/PXQ9ZU4.png"/>

-----------------------------------------------
 
<img src="https://i.imgur.com/HVior0F.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/uhYDSVI.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/8kUlYxI.png"/>

-----------------------------------------------

- <b>Setup a Client Computer and Login to it Using Active Directory Accounts</b>

1. Create a new virtual machine using Windows 11 ISO and place the VM on the same internal network as the Domain Controller.<br/>
2 Log in with one of the accounts that you created earlier and then test network connectivity by pinging “mydomain.com".<br/>
 
<img src="https://i.imgur.com/KtGloH0.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/HH6NZWK.png"/>

-----------------------------------------------
 
<img src="https://i.imgur.com/Fqw3fJn.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/jkuw9bI.png"/>

-----------------------------------------------


<img src="https://i.imgur.com/aSVUwTu.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/aHrRMur.png"/>

-----------------------------------------------


<img src="https://i.imgur.com/j8vknta.png"/>

-----------------------------------------------


