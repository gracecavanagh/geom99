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
7.	Input the username of the account. Then click Set, and a password will appear. Save this password somewhere because it will not reappear. However, you can rerun this process to get a new one if you need to.
   
 <img width="259" alt="Screenshot 2024-03-15 150749" src="https://github.com/gracecavanagh/geom99/assets/151089198/992396a3-dafe-4269-a2c2-19f588bff73d">

IMPORTANT: Now that your VM and firewall have been set up, make sure you know when your VM is stopped or not. The best way to stop it is using the 3 dots beside the VM instance and pressing “stop”. To turn it on, press “Start/Resume”.
 <img width="396" alt="Screenshot 2024-03-15 145331" src="https://github.com/gracecavanagh/geom99/assets/151089198/68b63ef6-29a7-4813-a18e-75e3d73eee2c">

1.	If it is on it will show a checkmark like this: ![image](https://github.com/gracecavanagh/geom99/assets/151089198/a07f7158-0be9-44d1-b6a7-2f5a40890414)

2.	If it is off it will show a stop sign like this:  ![image](https://github.com/gracecavanagh/geom99/assets/151089198/9f6053bc-1bfa-46ec-ad86-ef1975a36bc1)

3.	You can make sure it’s running by typing the external IP address into the web browser and if the Windows Information Services blue screen appears, the web server is replying.
