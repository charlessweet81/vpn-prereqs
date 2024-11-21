<p align="center">
<img src="https://i.imgur.com/hb8696w.png" alt="Proton VPN logo"/>
</p>

<h1>ProtonVPN - Installation & Configuring</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- ProtonVPN

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Step 1: Capture Your IP Address (Before Creating the VM)
- Step 2: Log in to Remote Desktop
- Step 3: 


<h2>Installation Steps</h2>
<h3>Step 1: Create Virtual Machine in Azure</h3>

<img src="https://i.imgur.com/LXakI0h.png" height="80%" width="80%" alt=""/>


- Action: Open a web browser on your actual computer (not a virtual machine) and go to https://whatismyipaddress.com/.
- Purpose: This shows your public IP address as assigned by your Internet Service Provider.
- Result: Copy the IP address shown on the page and save it in a text file (e.g., MyIP.txt) for reference.
<br /> 

<h3>Step 2: Create a Resource Group in Azure</h3>

<img src="https://i.imgur.com/LXakI0h.png" height="80%" width="80%" alt=""/>

- Action: Log into your Azure Portal at https://portal.azure.com.
- Navigate: Click on Resource Groups from the navigation menu on the left-hand side.
- Create Resource Group:
  - Click + Create or Add.
  - Enter a name for the resource group (e.g., "TestVMGroup").
  - Select a region for the resource group. (This can be your current location.)
  - Click Review + Create and then Create.

<br /> 

<h3>Step 3: Create a Windows 10 Virtual Machine</h3>

<img src="https://i.imgur.com/LXakI0h.png" height="80%" width="80%" alt=""/>

- Navigate: In the Azure Portal, search for Virtual Machines in the top search bar and select it.
- Create VM:
-   Click + Create and choose Azure Virtual Machine.
-   Under Basics, fill out the details:
  -   Select the previously created Resource Group.
  -   Give the VM a name (e.g., "TestVM").
  -   Choose an image: Windows 10 Pro or Enterprise.
  -   Select a region in a different country (e.g., Europe or Asia).
  -   Choose a size (e.g., Standard D2s_v3 for light use).
  -   Set admin username and password for login.
-   Click Review + Create, then Create.
-   Wait for Deployment: Once deployment completes, navigate to the VM's Overview page.

<br />

<h3>Step 4: Log Into the VM Using Remote Desktop</h3>

<p>
<img src="https://i.imgur.com/LXakI0h.png" height="80%" width="80%" alt=""/>
</p>

<br />

<h3>Step 4: Check the VM’s IP Address</h3>

<p>
<img src="https://i.imgur.com/LXakI0h.png" height="80%" width="80%" alt=""/>
</p>

<br />

<h3>Step 4: Sign Up for ProtonVPN on Your Computer</h3>

<p>
<img src="https://i.imgur.com/LXakI0h.png" height="80%" width="80%" alt=""/>
</p>

<br />

 Install ProtonVPN on the VM
