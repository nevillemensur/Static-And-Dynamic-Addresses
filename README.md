# Static-And-Dynamic-Addresses
<p align="center">
<img src=https://i.imgur.com/QdWOADa.png"/>
</p>

<h1>AWS - Objectives</h1>

-Analyze the difference between a statically and dynamically assigned IP addresses using EC2 instances

-Assign a persistent (static) IP to an EC2 instance

-Develop a solution to the customers issue found within this lab; after developing a solution, summarize and describe your findings

<br />

<h2>Ticket from the customer</h2>

Hello, Cloud Support!

We are having issues with one of our EC2 instances. The IP changes every time we start and stop this instance called Public Instance. This causes everything to break since it needs a static IP address. We are not sure why the IP changes on this instance to a random IP every time. Can you please investigate? Attached is our architecture. Please let me know if you have any questions.


Thanks!

Bob

Cloud Admin

<h2>Architecture diagram</h2>

<p>
<img src=https://i.imgur.com/1Pr6vtH.png>
</p>

<p>
Figure: Customer VPC architecture, which includes one public and one EC2 instance.
</p>
<br />





<h2>Environments and Technologies Used</h2>

- AWS Management Console

<h2>Operating Systems Used </h2>

- Mac OS</b> 

<h2>List of Prerequisites</h2>

Task 1: Investigate the customer's environment

Task 2: Send the Response to the customer
  

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
4. You should currently see one EC2 instance, which you can ignore for now. We will not use that instance since we will launch our own for task 1
</p>

<p>
<img src=https://i.imgur.com/s30Sb93.png/>
</p>

<p>
Figure: This is the EC2 dashboard where you can create instances and see an overall snapshot of current instances. 
</p>
<br />

<p>
5. From the top right corner, select Launch instances. This is how you will launch EC2 instances from the console.
</p>

<p>
<img src=https://i.imgur.com/SpkoS34.png/>
</p>


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
