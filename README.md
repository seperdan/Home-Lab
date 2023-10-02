# Home-Lab
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

<h2 align="center">Setup walkthrough</h2>

<b>For this setup, we will be using this network diagram:<b>
<img src="68747470733a2f2f692e696d6775722e636f6d2f496678766f59532e706e67.png">
<b>and utilizing VMware to create virtual setup of a Windows Server 2019 connecting to and managing a Windows 10 client. To start, download the Oracle VM VirtualBox, Microsoft Server 2019 ISO, and Microsoft Windows 10 ISO from the links under "Environments and Tools Used</h2>.
 

<br>Note: to obtain the Windows 10 ISO file, it's usually a little trickier than simply downloading it. you must first download the Windows 10 Media Creation Tool from the provided link (often called: "MediaCreationTool22H2.exe"). 

<img scr="2.png">
<img scr=1.png">

After running the Media Creation file, you will be presented with the option to Upgrade your Windows or create an installation media. Click on "create an installation media" option.

<img scr="3.png">

Then click on "ISO file" to create your Windows 10 ISO image file.

<img scr="4.png">

Now you have all your files:

<img scr="5.png">

</br>


