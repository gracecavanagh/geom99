Week 7 & 8 Step by Step Technical Log
Date: March 8, 2024 | Time Duration: 11pm to 11:30am | Total Time: 30 minutes.
GCP - Creating a VM and using the provided image 
(Done using Shawn’s video https://www.youtube.com/watch?v=dyFeyBX9jIY)
1.	Sign into GCP.
2.	Go to Compute Engine -> VM Instances.
3.	VM Instances -> Enable Compute Engine API.
![image](https://github.com/gracecavanagh/geom99/assets/151089198/437e16f8-d1e9-4d8d-ad74-5b915234fdbf)
4.	Click “My First Project” -> Create Instance
![image](https://github.com/gracecavanagh/geom99/assets/151089198/c9edde65-f379-4259-b28f-4b5832f5ebef)
5.	Change the boot disk to Windows -> under Boot Disk -> Custom Images change the “Source project for images” to the server that contains the image, select the image from the dropdown, then click Select.
6.	Scroll down, check off to allow HTTP and HTTPS traffic under Firewall. Then press Create.

Set Up Firewall Rules
(Done using Shawn’s video https://www.youtube.com/watch?v=dyFeyBX9jIY)
1.	At the VM instances page, select “Set up firewall rules” -> Create Firewall Rule.
 ![image](https://github.com/gracecavanagh/geom99/assets/151089198/fc0bd98f-d6e6-4736-a579-aa5251d5ce38)
2.	Under Direction of Traffic select Ingress and under Action on Match select Allow.
3.	Under Targets select All instances in the Network and under Source filter make sure it has selected IPv4 ranges.
4.	Under Source IPv4 ranges enter your External IP address (NOT internal, should not start with 10 or 192.168.) or if needed (not recommended) 0.0.0.0/0.
5.	Under Protocols and ports select TCP and enter 444, 6080, 6443. Then click Create.
Set Up Windows Password
(Done using Shawn’s video https://www.youtube.com/watch?v=dyFeyBX9jIY)
6.	Beside “RDP” click the down arrow and select “Set Windows Password”
   ![image](https://github.com/gracecavanagh/geom99/assets/151089198/657ec2cb-76b2-4c24-bd77-d29da0196f22)
7.	In this case, we are using a “student” account. Then click Set, and a password will appear. Save this password somewhere because it will not reappear. However, you can rerun this process to get a new one if you need to.
 ![image](https://github.com/gracecavanagh/geom99/assets/151089198/09ca1f41-84bc-4743-8c01-66560307d216)
IMPORTANT: Now that your VM and firewall have been set up, make sure you know when your VM is stopped or not. The best way to stop it is using the 3 dots beside the VM instance and pressing “stop”. To turn it on, press “Start/Resume”.
 ![image](https://github.com/gracecavanagh/geom99/assets/151089198/34d575b2-9530-428d-b03d-95ebffbe9b53)
1.	If it is on it will show a checkmark like this: ![image](https://github.com/gracecavanagh/geom99/assets/151089198/a07f7158-0be9-44d1-b6a7-2f5a40890414)

2.	If it is off it will show a stop sign like this:  ![image](https://github.com/gracecavanagh/geom99/assets/151089198/9f6053bc-1bfa-46ec-ad86-ef1975a36bc1)

3.	You can make sure it’s running by typing the external IP address into the web browser and if the Windows Information Services blue screen appears, the web server is replying.

Date: March 8, 2024 | Time Duration: 11:30pm to 12:30am | Total Time: 1 hour.
Connecting to the VM through Remote Desktop Connection
(Done using Shawn’s video https://www.youtube.com/watch?v=dyFeyBX9jIY)
1.	Open Remote Desktop Connection on your computer.
2.	Type in the current IP address allowed through the Firewall and :444. If it tries to log you in using your own personal username, make sure that after you click “Connect” you click “Show Options” to enter the correct username, in this case “student” and the password is the Windows password you saved in the previous section. After clicking OK, you can ignore the warning about a missing certificate and continue anyways. 
![image](https://github.com/gracecavanagh/geom99/assets/151089198/05a5e020-e9a7-4e3f-8862-2b64498f5752)
![image](https://github.com/gracecavanagh/geom99/assets/151089198/c7524407-2871-4ae0-9fbc-1e065976d12b)
3.	Now you should be inside the VM. Make sure to logoff properly in the Windows start bar, because just closing the screen doesn’t actually log you out.
   
Connecting to ArcGIS REST Endpoint and Manager
(Done using Shawn’s video https://www.youtube.com/watch?v=dyFeyBX9jIY)
1.	After the IP address in the search bar, add /arcgis/rest/services and it will take you to the REST endpoint. Now you know ArcGIS Server is running.
2.	To get to the Manager, add /arcgis/manager instead after the IP address.
**Spent about an hour because I had issues getting into the Server Manager without being on the VM itself and couldn’t understand why. Still have not been able to figure that out, tried multiple ports. I’ll be exploring that more in the future and updating. Also had to troubleshoot a bit with accessing the VM through the Remote Desktop but Lilit and I helped each other out.**

Date: March 8, 2024 | Time Duration: 12:30am to 2:00am | Total Time: 1.5 hours.
Consuming Server Data into ArcGIS Online
(Done partially using Shawn’s video https://www.youtube.com/watch?v=dyFeyBX9jIY)
1.	Open ArcGIS Pro->Insert->Connections->Server->New ArcGIS Server
2.	Add your IP address /arcgis as the Server URL, and username in this case is “siteadmin” and the password given in the checklist. Press OK and ignore the certificate pop-up.
 ![image](https://github.com/gracecavanagh/geom99/assets/151089198/1892aaa6-a691-48a8-9d9b-dc9b0b03c93d)
3.	In the catalog view, you can now access the SampleWorldCities Map Service. Add it to a new map.
 ![image](https://github.com/gracecavanagh/geom99/assets/151089198/f4019d71-4f78-4749-88ba-c0fb41417610)
4.	Click on Share -> share as Web Map
5.	Resolve all warnings and/or errors -> Click Share.
6.	Do NOT attempt to open this in AGOL when you have stopped the VM. It can lead to problems.
** It was easy to get everything set up but I spent a really long time troubleshooting. Even though my VM was still running, for some reason the entire map would just not show up in AGOL. Not even the basemap. I still do not know why. At first, it was because I only shared a certain part of the data which actually did allow a basemap to show up in AGOL, but never the actual Map Service. When I corrected myself and added the entire Map Service, absolutely nothing would show up in AGOL when I opened it in Map Viewer including a basemap. In the weeks to come I’ll be troubleshooting this again and adding it to logs because I couldn’t even resolve it by discussing it with classmates who were successful. ** 
 
