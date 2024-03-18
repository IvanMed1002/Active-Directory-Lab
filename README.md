<h1>Active Directory (IAM)</h1>

<h2>Lab Objective</h2>

<br>Install Windows Server 2019 on the new virtual machine in VirtualBox and add the Active Directory Domain Services role to the server. Promote the server to a domain controller and create a new domain while also configuring DHCP. Use a PowerShell script to create over 1,000 users in Active Directory. Create a new virtual machine with Windows 10 and join it to the domain. Log in to the Windows 10 virtual machine with one of the newly created user accounts. <br />

<h2>Environments Used </h2>

- <b>VirtualBox installed on host machine<b/>
- <b>Microsoft Server 2019 ISO<b/>
- <b>Windows 10 Enterprise ISO<b/>

<h2>Project Walk-Through Overview </h2>

- <b>Set up Virtual Envirnment </b>

1. Download and install VirtulBox<br/>
2. Download Microsoft Server 2019 iso from Microfsoft.<br/>
3. Create new VM with Microsoft Server 2019 as OS.<br/>

 
<img src="https://i.imgur.com/FgaNsrh.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/xJt4oBT.png"/>

-----------------------------------------------

- <b>Set Up Windows Server</b>

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

1. Log in to Windoes Server Vm as administrator and open "Server Manager" to "Add Roles and Features" <br/>
2. Promote the Virtula Machine to a Domain Controller (this will manage network secuirties and allow users to authenticate and access network  resources).

 
<img src="https://i.imgur.com/k4q9YXG.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/DVa0Zgx.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/DQtE10F.png"/>

-----------------------------------------------

<img src="https://i.imgur.com/9zXA6vw.png"/>

-----------------------------------------------
2. Promote the Virtula Machine to a Domain Controller (this will manage network secuirties and allow users to authenticate and access network  resources).

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



- <b>Create a dediccated domain administrator account and then give it admin privileges</b>

1. Open the Active Directory Users and Computers tool on your domain controller <br/>
2. Create new organization unit named "_ADMINS_" and create user called "admin".
3. Add "admin" user to domain group to make user a member of "domain admins" 

 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------




- <b>Configure a Dynamic Host Configuration Protocol (DHCP)</b>

1. Install the DHCP server role in Server Manager (this will allow automatically assign IP addresses)<br/>
2. Create a new DHCP scope for IP address range and subnet mask.
3. Authorize the DHCP server to allow the DHCP server to provide IP addresses to devices on the network.
 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------




- <b>Run a PowerShell Script to Create Users in Active Directory</b>

1. Instead of manually creating each user, we’ll use a PowerShell script to create over 1000 users at once.<br/>
2. Enable “drag and drop” between your host and guest machine to allow scipt file to be downloaded from host machine and tranfered over to VM machine.
3. Run script as Administrator in PowerShell ISE.

 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------
 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------


- <b>Setup a Client Computer and Login to it Using Active Directory Accounts</b>

1. Create a new virtual machine using Windows 11 ISO and place the VM on the same internal network as the Domain Controller.<br/>
2 Log in with one of the accounts that you created earlier and then test network connectivity by pinging “mydomain.com.”


 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------
 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------











- <b></b>

1. <br/>


 
<img src=""/>

-----------------------------------------------

<img src=""/>

-----------------------------------------------


















