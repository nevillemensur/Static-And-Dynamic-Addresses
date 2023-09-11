# Static-And-Dynamic-Addresses
<p align="center">
<img src=https://i.imgur.com/QdWOADa.png"/>
</p>

<h1>AWS - Objectives</h1>

-Summarize and investigate the customer scenario

-Analyze the difference between a private and public IP address

-Develop a solution to the customer's issue in this lab

<br />

<h2>Ticket from the customer</h2>

Hello, Cloud Support!

We currently have one virtual private cloud (VPC with a CIDR range of 10.0.0.0/16. In this VPC, we have two Amazon Elastic Compute Cloud (Amazon EC2) instances: instance A and instance B. Even though both are in the same subnet and have the same configurations with AWS resources, instance A cannot reach the internet, and instance B can reach the internet. I think it has something to do with the EC2 instances, but I'm not sure. I also had a question about using a public IP address such as 12.0.0.0/16 for a VPC that I would like to launch. Would that cause any issues? Attached is our architecture for reference.


Thanks!

Jess

Cloud Admin

<p>
<img src=https://i.imgur.com/NpI57NW.png/>
</p>

<p>
Figure: The customer's architecture, which consists of a VPC, internet gateway, public subnet with instance A, and a public subnet with instance B.
</p>
<br />





<h2>Environments and Technologies Used</h2>

- AWS Management Console
- Remote Desktop SSH


<h2>Operating Systems Used </h2>

- Mac OS</b> 

<h2>List of Prerequisites</h2>

Task 1: Investigate the customers enviroment

Task 2: Use SSH to connect to instance A and instance B
  

<h2>Task Steps</h2>

<p>
1. Start by opening the AWS Management Console.
</p>

<p>
<img src=https://i.imgur.com/t6XWmwm.png/>
</p>
<br />

<p>
2. Once you are in the AWS console, type EC2 in the search bar on the top left corner and select EC2 from the list.
</p>

<p>
<img src=https://i.imgur.com/cvwNAWN.png/>
</p>
<br />

<p>
3. You are now in the Amazon EC2 dashboard. In the left navigation menu, choose Instances. This option takes you to your current EC2 instances
</p>

<p>
<img src=https://i.imgur.com/IFm5LbV.png/>
</p>
<br />

<p>
4. Copy and paste the names and IP addresses of both instances for future reference in a text editor. Select the check box next to instance A. At the bottom of the page, choose the Networking tab, and note the Public and Private IPv4 addresses. Once you copy and paste the name and IP addresses, deselect the instance, and then select instance B and do the same
</p>

<p>
<img src=https://i.imgur.com/Kg8tLLb.png/>
<img src=https://i.imgur.com/lcX9sBx.png/>
</p>

<p>
Figure: Amazon EC2 instance A networking information. 
</p>
<br />

<p>
<img src=https://i.imgur.com/5hJmUf9.png/>
<img src=https://i.imgur.com/ivbC3GR.png/>
</p>

<p>
Figure: Amazon EC2 instance B networking information.
</p>
<br />

<h2>Task 2 Steps</h2>

<p>
1. Download PEM file and save the labsuser.pem file
<img src=https://i.imgur.com/uWCrR13.png/>
</p>
<br />

<p>
2. Open a terminal window, and change directory cd to the directory where the labsuser.pem file was downloaded. For example, if the labuser.pem file was saved to your Downloads directory, run this command: cd ~/Downloads <img src=https://i.imgur.com/xbtTCBI.png/>
</p>
<br />

<p>
3. Change the permissions on the key to be read-only, by running this command: chmod 400 labsuser-7.pem <img src=https://i.imgur.com/T5v67gr.png/>
</p>
<br />

<p>
4. Run the command: ssh -i labsuser-7.pem ec2-user@10.0.10.102. We were not able to connect to instance A. <img src=https://i.imgur.com/gjyhCl7.png/>
</p>
<br />

<p>
5.Run the command: ssh -i labsuser-7.pem ec2-user@35.91.189.114. We were able to connect to instance B using the public IP address. <img src=https://i.imgur.com/zuK7VZ4.png/>
</p>
<br />

<h2>Recap</h2>

<p>
In this lab you have investigated the customer's environment and applied troubleshooting techniques that allowed you to resolve the customers’ issue. Within the scenario, you discovered that the customer's EC2 instance (instance A) needed a public IP address to connect to the internet. This was tested by using an SSH utility to connect to the instance. Private IP addresses are used within the VPC and cannot establish a connection to the internet
</p>
<br />
