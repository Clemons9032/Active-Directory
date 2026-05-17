<p align="center">

 
<img width="866" height="650" alt="image" src="https://github.com/user-attachments/assets/5e7866cc-ac94-4540-8b0b-ef76f1e59b3a" />

<h1>Active Directory- High level Installation and Deployment
This is a project showcasing how to set up an active directory environment using microsoft's azure cloud infrastructure. This project will also be accompanied with a full video breakdown linked to my youtube channel.

<h2>Video Demonstration</h2>



 [![My Skills](https://skillicons.dev/icons?i=azure,windows)](https://skillicons.dev)


 
 -Microsoft Azure
 
 -Remote Desktop Protocol
 
 -Windows Server 2022

 Operating Systems Used </h2>


 <img width="700" height="417" alt="image" src="https://github.com/user-attachments/assets/2a5f0107-6016-4887-be55-035130165652" />


<h2>List of Prerequisites</h2>


-Microsoft Azure Account

-2 Virtual Machines

<h2>High-Level Deployment and Installation Steps</h2>


> [!Important]
> Each step will include written instructions and corresponding screenshots. Expand the See Screenshots section to view the images and progress through the portfolio.


<h3>1. Create Windows 11 VM <h3>
<p>So we're going to make our vm using the azure portal. Click on virtual machines and select create new. I'm going to name my vm client1 but if you're following along, you can name your vm whatever you want. Just make sure it's easy enough for you to remember the purpose of each vm. I'm going to place this vm in East US 2 region.

<details><summary>See screenshots</summary>
<img src="images/AD_Step19.png" >
</details>

**Notes**
So there's a tab called resource groups and this is where i'm going to put my domain controller and my client1 vm. The reason for this is because it's the only way I can get these two vms to properly communicate with each other. If the vms are in two different resource groups then they won't be able to communicate and I wouldn't be able to join my client to the domanin controller so it's very important to put both virtual machines in the same resource group. I chose the name Active_Directory_Lab for my resource group for ease of use.

<details><summary>See screenshots</summary>
<img src="images/AD_Step3.png" >
</details>



For the iso, i'm going to choose the windows 10 operating system. After the iso has been chosen, I'm going to choose a username and password for my login credentials. After I've typed in my credentials, I'm going to continue to the bottom and make sure to check box asking if I have a windows image. 

<details><summary>See screenshots</summary>
<img src="images/AD_Step20.png" >
</details>



<details><summary>See screenshots</summary>
<img src="images/AD_Step21.png" >
</details>


Next, I'm going to go to the network tab and make sure that both vms that are created are in the same virtual network. If it's not in the same virtual network then they won't be able to communicate with each other when it's time to set up the Active Directory.

<details><summary>See screenshots</summary>
<img src="images/AD_Step32.png" >
</details>


So after checking sure that the vm is in the right virtual network, just go to review and create and azure will start a final validation. Once the validation completes, then we can start to create the virtual machine.


<details><summary>See screenshots</summary>
<img src="images/AD_Step33.png" >
</details>


<h3> Step 2. Create DC Virtual Machine
<p>Now I'm going to set up the Domain Controller using Windows Server 2022. Click on the virtual machines tab and click create new virtual machine. I named my Domain Virtual machine DC-1. I'm going to choose the Active_Directory_Lab resource group again for this virtual machine. It has to stay in the same resource group as my client1 vm.


<details><summary>See screenshots</summary>
<img src="images/AD_Step3.png" >
</details>


<details><summary>See screenshots</summary>
<img src="images/AD_Step4.png" >
</details>

Choose a username and password to login with on the virtual machine. Just make sure to write it down in notepad so you don't forget it. After that, go to the bottom of the page and click on the acceptance button


<details><summary>See screenshots</summary>
<img src="images/AD_Step5.png" >
</details>


After choosing your credentials, finish up by navigating to the bottom of the page and clicking the license agreement that asks if you have a windows install license. Next click on the network tab and make sure it's in the proper virtual network that the client vm is located in. Now click on review & create and once the validation check has passed, continue to creating your vm.



<details><summary>See screenshots</summary>
<img src="images/AD_Step6.png" >
</details>



<details><summary>See screenshots</summary>
<img src="images/AD_Step7.png" >
</details>

