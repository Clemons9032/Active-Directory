<p align="center">
  <img width="866" height="650" alt="Active Directory Setup" src="https://github.com/user-attachments/assets/5e7866cc-ac94-4540-8b0b-ef76f1e59b3a" />
</p>

<h1>Active Directory - High Level Installation and Deployment</h1>

<p>This is a project showcasing how to set up an active directory environment using Microsoft's Azure cloud infrastructure. This project will also be accompanied with a full video breakdown linked to my portfolio.</p>

<h2>Video Demonstration</h2>

[![My Skills](https://skillicons.dev/icons?i=azure,windows)](https://skillicons.dev)

- Microsoft Azure
- Remote Desktop Protocol
- Windows Server 2022

<h2>Operating Systems Used</h2>

<img width="700" height="417" alt="Operating Systems" src="https://github.com/user-attachments/assets/2a5f0107-6016-4887-be55-035130165652" />

<h2>List of Prerequisites</h2>

- Microsoft Azure Account
- 2 Virtual Machines

<h2>High-Level Deployment and Installation Steps</h2>

> [!Important]
> Each step will include written instructions and corresponding screenshots. Expand the "See screenshots" section to view the images and progress through the portfolio.

<h3>1. Create Windows 11 VM</h3>

<p>So we're going to make our VM using the Azure portal. Click on virtual machines and select create new. I'm going to name my VM client1 but if you're following along, you can name your VM whatever you like.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step19.png" alt="Step 19: Create VM">
</details>

<p><strong>Notes:</strong> There's a tab called resource groups and this is where I'm going to put my domain controller and my client1 VM. The reason for this is because it's the only way I can get these two VMs to properly communicate with each other.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step3.png" alt="Step 3: Resource Groups">
</details>

<p>For the ISO, I'm going to choose the Windows 10 operating system. After the ISO has been chosen, I'm going to choose a username and password for my login credentials. Make sure to write down your credentials in notepad so you don't forget them.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step20.png" alt="Step 20: OS Selection">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step21.png" alt="Step 21: Credentials">
</details>

<p>Next, I'm going to go to the network tab and make sure that both VMs that are created are in the same virtual network. If it's not in the same virtual network then they won't be able to communicate with each other.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step32.png" alt="Step 32: Network Configuration">
</details>

<p>After checking sure that the VM is in the right virtual network, just go to review and create and Azure will start a final validation. Once the validation completes, then we can start to create the VM.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step33.png" alt="Step 33: Review and Create">
</details>

<h3>Step 2. Create DC Virtual Machine</h3>

<p>Now I'm going to set up the Domain Controller using Windows Server 2022. Click on the virtual machines tab and click create new virtual machine. I named my Domain Virtual machine DC-1.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step3.png" alt="Step 3: Resource Groups">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step4.png" alt="Step 4: VM Configuration">
</details>

<p>Choose a username and password to login with on the virtual machine. Just make sure to write it down in notepad so you don't forget it. After that, go to the bottom of the page and click on the accept button.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step5.png" alt="Step 5: Credentials Setup">
</details>

<p>After choosing your credentials, finish up by navigating to the bottom of the page and clicking the license agreement that asks if you have a Windows install license. Next click on the network tab and ensure it's on the same virtual network as client1.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step6.png" alt="Step 6: License Agreement">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step7.png" alt="Step 7: Network Tab">
</details>

<h3>Step 3. Configure Static IP on Domain Controller</h3>

<p>Once Azure has finished deploying the Windows Server VM, I'm going to go and set it up as a static IP. The reason for this is because I don't need the IP address changing because it'll make it harder to connect to the domain controller later on.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step9.png" alt="Step 9: Static IP Setup">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step10.png" alt="Step 10: IP Configuration">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step11.png" alt="Step 11: Static IP Assignment">
</details>

<p>Now that I've turned the IP address of DC-1 machine into a static IP address, I'm going to log into my DC-1 VM. Once logged in, the Windows Server manager will appear and from there, I'm going to turn off the firewall to allow communication between the VMs.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step16.png" alt="Step 16: DC Login">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step17.png" alt="Step 17: Server Manager">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step18.png" alt="Step 18: Firewall Configuration">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step33.png" alt="Step 33: Firewall Disabled">
</details>

<p>After I turn the firewall off on DC-1, I'm going to configure client1 DNS server to point it to my domain controller. I'm going to click on virtual machines in Azure and double-click on client1. Next, I'll go to the network settings and update the DNS configuration.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step22.png" alt="Step 22: Client DNS Configuration">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step23.png" alt="Step 23: DNS Settings">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step24.png" alt="Step 24: DNS Server Assignment">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step25.png" alt="Step 25: DNS Verification">
</details>

<h3>Step 4. Log into client1</h3>

<p>I'm going to get the public IP address of client1 and remote desktop into the VM. Once inside of client1, I'm going to open PowerShell and ping my domain controller IP address. It should respond back successfully if everything is configured correctly.</p>

<details><summary>See screenshots</summary>
<img src="images/AD_Step29.png" alt="Step 29: Get Public IP">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step30.png" alt="Step 30: Remote Desktop Connection">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step31.png" alt="Step 31: PowerShell Ping">
</details>

<details><summary>See screenshots</summary>
<img src="images/AD_Step34.png" alt="Step 34: Ping Successful">
</details>

> [!Important]
> I'm going to continue the installation documentation of Active Directory in another portfolio. In order to get the best understanding of the following steps, make sure to read this documentation before proceeding to the next part of the installation process.
