<h1>Sentinel Lab</h1>

<h2>Description</h2>
In this lab, I learned to create a honeypot using azure sentinel which is a cloud-based security information and event manager(SIEM). I used Azure's cloud-based virtual machines as the honeypot and made it vulnerable to the internet for potential attacks. The data was recieved by monitoring the attacks from the honeypot and creating custom logs that can sort information like country and being able to apply it to the world map.
<br />


<h2>Languages and Environments Used</h2>

- <b>PowerShell</b> 
- <b>Remote Desktop Connection</b>
- <b>Azure</b>
- <b>Ip geolocation</b>

<h2>Lab walk-through:</h2>

<p align="center">
<b>Step 1: Create Azure Account & Virtual Machine as honeypot</b> 
<img src="https://i.imgur.com/liN1p7L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</br>
</br>
<img src="https://i.imgur.com/oovXsUy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
<b>Step 2: Create log analytics</b>  <br/>
Now a log analytics workspace is created. The reason to create a log is to find where the attacks are orginating from.
<img src="https://i.imgur.com/7G1hzfe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/J4wlXZl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 3: Microsoft defender for the cloud settings</b> <br/>
In order to actually gather logs from our virutal machine, you need to configure settings in microsoft defender. Click "environment settings" and on the VM created click "enable all microsoft defender for cloud plans".
<img src="https://i.imgur.com/QoSXclh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FnRJeBO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 4: Add Microsoft sentinel to workspace & open Remote desktop connection</b>  <br/>
<img src="https://i.imgur.com/3OBu3V7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/XhQsPcy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 5: Open Event Viewer <br/>
On the virutal machine, open event viewer from the start menu. On purpose, input username and password incorrectly to see that attempted login later. Settings were also changed to make the virtual machine easier to find.
<img src="https://i.imgur.com/H9jIKED.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5qpga0i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/pImETqY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/ZiFOJJg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/nuAYxUm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 6: Adding Powershell script </b>  <br/>
After adding in the Powershell script from github repo and saving the file on our VM, get your own API key from ipgeolocation.io. The script is run and you can see users already trying to get access into vm from all over the country.
<img src="https://i.imgur.com/UcdUQ0H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/x9axYDF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<b>Step 7: Create Custom Logs</b> <br/>
Creating custom logs in our log analytics workspace is important to add the geodata from the VM. Copy the "failed_rdp" file and open it to our workspace. </br>
<img src="https://i.imgur.com/gUJu8mR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<b>Step 8: View failed login attempt</b>
<br/>
<br />
<img src="https://i.imgur.com/1vR29yg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br>Step 9: World Map of attacks </b>  <br/>
After customizing log and adding the "failed_rdp.log" file we created, give it 10-15 minutes to see where in the country users are able to attempt to log into our VM. The configurations on the bottom are organzied to make the information easier to read. Leaving the VM for a longer period of time provides a real-time event map!
<img src="https://i.imgur.com/S8VH0fK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>
