<h1>Basic Virtual Machine and Active Directory Home Lab Set up</h1>

<h2>Description</h2>
<b>I made this project to serve as a general walkthrough for people to set up Actice Directory, DNS, DHCP, NAT and RAS in an emulated enterprise setting!</b>

<h2>Utilities a& Services Used and Created</h2>
<br>- Powershell</br> 
<br>- Server Manager</br>
<br>- Active Directory</br>
<br>- DNS</br>
<br>- DHCP</br>
<br>- NAT</br>
<br>- RAS</br>

<h2>Environments and Tools Used</h2>
<br>Oracle VM VirtualBox: https://www.virtualbox.org/wiki/Downloads</br>
<br>Microsoft Server 2019: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019</br>
<br>Microsoft Windows 10 ISO: https://www.microsoft.com/en-us/software-download/windows10</br>

<h2 align="center">Virtual Machine Setup Walkthrough</h2>

<b>For this setup, we will be using this network diagram:<b>
<img src="68747470733a2f2f692e696d6775722e636f6d2f496678766f59532e706e67.png" height="80%" width="80%" alt="Network Diagram"/>
<b>and utilizing VMware to create virtual setup of a Windows Server 2019 connecting to and managing a Windows 10 client. To start, download the Oracle VM VirtualBox, Microsoft Server 2019 ISO, and Microsoft Windows 10 ISO from the links under "Environments and Tools Used</h2>.
 

<br>Note: to obtain the Windows 10 ISO file, it's usually a little trickier than simply downloading it. you must first download the Windows 10 Media Creation Tool from the provided link (often called: "MediaCreationTool22H2.exe"). 

<img src="2.png" width="70%" height="70%" alt=Download Page>
</br>
<img src="1.png" width="70%" height="70%" alt=Windows 10 Media Creation Tool>
</br>
<b>After running the Media Creation file, you will be presented with the option to Upgrade your Windows or create an installation media. Click on "create an installation media" option.</b>
<img src="3.png" width="70%" height="70%" alt=ISO file creation>

Then click on "ISO file" to create your Windows 10 ISO image file.

<img src="5.png" width="70%" height="70%" alt=ISO file creation2>

Now you have all your files:

<img src="4.png" width="70%" height="70%" alt=ISO file>
</br>

<b>Once we have installed all the ISO files installed, appointing the Windows 10 ISO to "SeperClientLab" and Windows 2019 Server ISO to "SeperServerLab" it should look a little something like this:<b>

<img src="6.png" width="70%" height="70%" alt=Overall VM setup>

<h2 align="center">Server Configuration Walkthrough</h2>

<b>We'll start off with setting up the Server first. Click on the Server's settings tab and navigate to "Adaptor 2". Click "Enable Network Adapter" and make it attached to the internal network "intnet" as shown below:</b>

<img src="7.png" width="70%" height="70%" alt=Server Configuration>

<b>This creates an internal network to attach to the NAT network that's configured in Adapter 1. Now load the Server ISO image to boot the virtual server!</b>

<img src="8.png" width="70%" height="70%" alt=Booting screen>

<b>First order of business is to set up the internet by configuring the two network adapters. One is for the internal NIC and the other for the external so we'll have to configure them. Navigate to Network Settings and click on "Change adapter options."</b>

<img src="9.png" width="70%" height="70%" alt=Adapter Settings>

<b>Once there, you will have two network options. One will be the external and other for the internal networks but you will have to configure these as such.</b>

<img src="10.jpeg" width="70%" height="70%" alt=Network Connections>

<b>Right click on one and click on "Properties." Then double click on "Internet Protocol Version 4 (TCP/IPv4)" to configure it as the internal network. Based on our Network Diagram, configure the IP address, Subnet mask, and DNS server address.</b>

<img src="11.png" width="70%" height="70%" alt=TCP/IPv4>
<img src="12.png" width="70%" height="70%" alt=Address Configuration>

<b>In this virtual environment, the Domain Controller will act as our default gateway, so we do not need to add a default gateway address. And for the DNS server, I assigned it to a loopback address so that it will ping itself.</b>


<br>Now, open Server Manager and click on "Add roles and features"<br>
<img src="13.png" width="70%" height="70%" alt=Active Directory>

and by following this short clip, install the Active Directory, DHCP, DNS, NAT, and RAS!

https://github.com/seperdan/Home-Lab/assets/54723844/99b0c875-6b03-4e0c-becf-9121d7f3abcb

<b>Once this is doen, we we will need to create a Domain to go with the Active Directory Domain Services (AD DS) we just set up.


