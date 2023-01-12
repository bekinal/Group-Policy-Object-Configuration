<h1>Group Policy Object Configuration</h1>

<h2>Description</h2>
Project consists of using Active Directory tools to create and maintain Group Policy across the domain. This project assumes that a Windows 10 Client has been installed and added to the domain.
<br />


<h2>Utilities Used</h2>

- <b>VirtualBox</b> 
- <b>Windows Server 2016</b>
- <b>Windows 10</b>

<h2>Environments Used </h2>

- <b>Windows Server 2016</b>

<h2>Users and Groups:</h2>

Open the domain controller and select Tools, Group Policy Management: <br/>
<img src="https://imagizer.imageshack.com/img924/6609/32DoS8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigate to "Forest:cyber.local/Domains/cyber.local" and right click the Sales OU. Select Create a GPO in this domain, and link it here". Name the new GPO "Disable Control Panel": <br/>
<img src="https://imagizer.imageshack.com/img923/4743/l36qdC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select OK: <br/>
<img src="https://imagizer.imageshack.com/img924/5631/g9iDeN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right-click the GPO and click Edit: <br/>
<img src="https://imagizer.imageshack.com/img922/4453/ktvAb2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Naviagte to "User Configuration/Policies/Administrative Templates: Policy/Control Panel" and click it. On the right side of the screen, right-click "Prohibit access to Control Panel and PC Settings" and choose Edit: <br/>
<img src="https://imagizer.imageshack.com/img924/9045/MW3XQy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Enabled and click Apply, Next: <br/>
<img src="https://imagizer.imageshack.com/img922/5273/2LeyIe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Exit the window and create another GPO in the Sales OU following the same method. This object will be named "Disable CMD": <br/>
<img src="https://imagizer.imageshack.com/img924/2989/ehMKCM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right click the object and select Edit: <br/>
<img src="https://imagizer.imageshack.com/img922/8139/32MeDd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigate to "User Configuration/Policies/Administrative Templates/System" and click it. On the right side, right click "Prevent access to the command prompt" and choose Edit: <br/>
<img src="https://imagizer.imageshack.com/img924/4536/m5A64s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On the next window, check Enabled and click Apply, then OK: <br/>
<img src="https://imagizer.imageshack.com/img923/508/w4Cay6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Exit the window and create another GPO under the Sales OU called Disable Registry Editor: <br/>
<img src="https://imagizer.imageshack.com/img922/5488/0R3TXB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Right click the newly created GPO and select Edit: <br/>
<img src="https://imagizer.imageshack.com/img922/3446/rxIDJ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Navigate to "User Configuration/Policies/Administrative Templates/System" and click it. On the right side, right click "Prevent access to registry editing tools" and choose Edit: <br/>
<img src="https://imagizer.imageshack.com/img923/8864/XVxWPe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Check enabled and click Apply, OK: <br/>
<img src="https://imagizer.imageshack.com/img924/5102/wBowqU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On the left pane, right click the cyber.local domain and choose "Create a GPO in this domain, and Link it here". Create a new GPO named "Disable Recycle Bin". Right click the new GPO and select Edit. Navigate again to "User Configuration/Policies/Administrative Templates/Desktop" and click it. Right-click "Remove Recycle Bin icon from desktop" and choose Edit: <br/>
<img src="https://imagizer.imageshack.com/img924/8341/kVdepO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select Enabled and click Apply, OK: <br/>
<img src="https://imagizer.imageshack.com/img922/2592/lzqiEl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log into the Windows 10 VM using Salesperson1. Since Salesperson1 was not previously used, the new policies should auto-update. If not, open the CMD and run "gpupdate /force": <br/>
<img src="https://imagizer.imageshack.com/img924/5083/4LN8T7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Note that the reycle bin does not appear on the desktop: <br/>
<img src="https://imagizer.imageshack.com/img924/539/SaFiTv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Press "Windows key + R" and type CMD : <br/>
<img src="https://imagizer.imageshack.com/img923/9963/ahbEjo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Note that this user does not have access: <br/>
<img src="https://imagizer.imageshack.com/img923/1311/1fWNwP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the run command menu and type "control": <br/>
<img src="https://imagizer.imageshack.com/img922/8062/DLtPPn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Notice that this user is restricted: <br/>
<img src="https://imagizer.imageshack.com/img924/8531/JtWcTQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Repeat that process for "regedit": <br/>
<img src="https://imagizer.imageshack.com/img923/8136/EeAaSQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Notice that the user does nto have access: <br/>
<img src="https://imagizer.imageshack.com/img922/6251/TtI9Ub.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
