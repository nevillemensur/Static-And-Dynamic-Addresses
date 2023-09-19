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
  

<h2>Task 1: Investigate the customer's environment</h2>

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

<p>
6. Follow the steps below to complete the creation of an Amazon EC2 instance.

Step 1: In the Names and Tags section give your instance a name. In this example, I will label our instance "Test Instance"

<p>
<img src=https://i.imgur.com/HUTc8PP.png/>
</p>

Step 2: Choose an Amazon Machine Image (AMI): 

Select the first entry for Amazon Linux 2 AMI (HVM)

An AMI is a template that contains the OS and configuration of the EC2 instance.

<p>
<img src=https://i.imgur.com/LKO8GGA.png/>
</p>


Step 3: Choose an Instance Type:

Select t3.micro and navigate to the bottom of the window and click the button edt: Network settings

<p>
<img src=https://i.imgur.com/HXLrDoJ.png/>
</p>


Step 4: Network settings:

Network: Choose vpc-xxxxxxxx | Lab VPC

Subnet: Choose subnet-xxxxxx | Public Subnet 1

Auto-assign Public IP: Set to enable

<p>
<img src=https://i.imgur.com/wAG1zJR.png/>
</p>


Step 5: Configure Security Group: 

Under Assign a security group, select the Select an existing security group radio button and select the security group with the name Linux Instance SG. Then navigate to the bottom of the window and hit Review and Launch.

<p>
<img src=https://i.imgur.com/krZDUWL.png/>
</p>



Step 6: Review Instance Launch:

Navigate to the bottom of the window and hit Launch.

A pop-up window asks you to select an existing key pair or create a new key pair.

In the first drop down, keep Choose an existing key pair.

In the second drop down, select the key pair vockey | RSA.

Check the box underneath the second drop down. Once checked, select Launch Instances.

<p>
<img src=https://i.imgur.com/XjcLqzq.png/>
</p>

<p>
<img src=https://i.imgur.com/BB6u0kE.png/>
</p>

<p>
<img src=https://i.imgur.com/09CCDzS.png/>
</p>

<p>
<img src=https://i.imgur.com/XjcLqzq.png/>
</p>


Step 7: Add Tags:

Navigate to the instance page and check the "Test Instance" box

Select Tag and click Manage tags.

Under Key enter Name and under Value enter test instance then click save.

<p>
<img src=https://i.imgur.com/tSNhZv4.png/>
</p>


<p>
<img src=https://i.imgur.com/gwRQGeP.png/>
</p>

<p>
<img src=https://i.imgur.com/RVFJDul.png/>
</p>

10. Return to the EC2 dashboard and see the EC2 instance that was just created. Select test instance. Under the Instance state, you will see Initializing. Wait until it says 2/2 before continuing.

<p>
<img src=https://i.imgur.com/Tk6XAzT.png/>
</p>
Figure: Instances go through states, just like when a computer is booting up. When it is ready to use, the state will say "running" and you will be able to use it for services like SSH.
<br />




<p>
  
11. Select the checkbox of your test instance. At the bottom, select the Networking tab. In this tab, observe and note the Public IPv4 address and the Private IPv4 address. Once noted, navigate to the top right of the window, select the Instance state drop-down button, and select Stop instance. Once the Instance state changes to Stopped, navigate back down to the tabs and observe the Public and Private IPv4 address.
<img src=https://i.imgur.com/B4uKArT.png/>
</p>

Figure: This is the networking tab for instances. This shows any networking configurations related to the instance such as public and private IPv4 addresses and public and private IPv4 DNS.

<p>
<img src=https://i.imgur.com/2fuTum9.png/>
</p>

Figure: To start, stop, or terminate an instance, navigate to the top of the EC2 dashboard and select the "Instance state" button.
<br />



<p>
  
12. Now restart the test instance by navigating to the top window and selecting the Instance state and Start instance. Wait until the Instance state changes to Running. Take note of the Public and Private IPv4 addresses. What did you notice between the public and private IP addresses when you stopped and started the EC2 instance? Would you consider this the Public IP a static or dynamic IP address? What would you consider the Private IP address for the EC2 instance? Do you think we have replicated the customer's issue?
    
</p>
<br />

<p>
<img src=https://i.imgur.com/NjYofu6.png/>
</p>
Figure: By starting the instance, you can see the details populate in the Networking tab.
<br />



<p>
  
13. We still haven't solved the customer's issue. Bob needs a permanent Public IP address that doesn't change when he stops and restarts his instance. AWS does have a solution that allocates a persistent public IP address to an EC2 instance, called an Elastic IP (EIP). From the EC2 dashboard, navigate to Network and Security on the left navigation and select Elastic IPs. Notice that there are no EIPs. Create one by selecting the button Allocate Elastic IP address in the top right. Keep everything as default and hit Allocate. Take note of the EIP address.
    
</p>

<p>
<img src=https://i.imgur.com/6AxXGoG.png/>
</p>

Figure: Within the EC2 dashboard, under "Network and Security" in the left navigation, select "Elastic IPs"
<br />

<p>
  
14. Select the EIP you just created by selecting the checkbox. Now attach this permanent, public IP address to the dynamic instance by navigating to the top right and navigating to Actions and Associate Elastic IP address.
    
</p>

<p>
<img src=https://i.imgur.com/yvvegcy.png/>

Figure: The EIP created will now be associated to the EC2 instance by going to the actions menu and selecting "Associate Elastic IP address".
<br />

</p>

<p>
  
15. Leave the resource type as Instance, and select test instance from the Choose an Instance drop down menu. Under Private IP address, select the empty box. The Private IP associated with that instance is selected. Click the Associate button

<p>
<img src=https://i.imgur.com/vRgFLWA.png/>
</p>


16. Navigate back to the Instances page using the left navigation pane. Select the checkbox for the test instance and navigate to the Networking tab. Take note of the Public IPv4 address. Did you notice that the EIP address is now the Public IP address? Now stop and start the instance and observe the differences. What did you observe? Is this a static or dynamic IP address? Did you solve the customer's issue? Why or why not?

<p>
<img src=https://i.imgur.com/w5rPjrX.png/>
</p>

<h2>Task 2: Response to the customer </h2>

Subject: Re: Issue with IP Address for Public Instance

Hello Bob,

Thank you for reaching out to Cloud Support regarding the issue with the IP address for your EC2 instance, Public Instance. I understand the frustration this must be causing, and I'm here to help you resolve this problem.

The reason your EC2 instance's IP address changes every time you start and stop it is due to the absence of an Elastic IP address associated with it. When you launch an EC2 instance without allocating a public IP address or attaching an Elastic IP, AWS assigns a dynamic public IP address. This dynamic IP address is subject to change whenever the instance is stopped and started again.

To fix this issue and provide your EC2 instance with a static IP address, we recommend associating an Elastic IP address with it. An Elastic IP address is a static, public IPv4 address that remains the same even if the instance is stopped and started. This ensures consistent connectivity for your applications and services.

Here's how you can associate an Elastic IP address with your EC2 instance:

Sign in to the AWS Management Console.
Navigate to the EC2 Dashboard.
In the navigation pane, under "Network & Security," select "Elastic IPs."
Choose "Allocate new address" and then select "Allocate."
After the allocation is complete, select the newly created Elastic IP address.
Click on the "Actions" button, and choose "Associate IP address."
In the Associate Elastic IP address dialog box, select the instance you want to associate with the Elastic IP address (in your case, Public Instance).
Confirm the association, and the Elastic IP address will now be linked to your EC2 instance.
This should resolve the issue of your EC2 instance's IP address changing upon restart. Please make sure to update your DNS records or configurations to use the Elastic IP address for consistent connectivity.

If you have any further questions or encounter any difficulties during this process, please feel free to reach out to us. We're here to assist you.

Best regards,

Neville Mensur


<h2>Recap</h2>

In this lab, you have investigated the customer's environment and applied troubleshooting techniques that allowed you to resolve the customers’ issue. Within the scenario, you discovered that the customer Amazon EC2 instance (public instance) had a dynamic IP address which caused it to constantly change IPs when the instance was stopped and started. In order to fix this issue, you suggested attaching an EIP in order for the IP to become persistent (static). This was tested by SSHing into the test instance and starting and stopping it with a dynamic IP address.

