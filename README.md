# AWS Security Traffic Monitoring and Packet Analysis


<h2>Description</h2>
This lab demonstrates configuring Amazon VPC Traffic Mirroring. In this hands-on exercise, I set up Traffic Mirroring, configure filters, and capture network traffic for in-depth analysis. 
<br />


<h2>Services Used</h2>

- <b>AWS EC2</b> 
- <b>AWS VPC</b>

<h2>Environments Used </h2>

- <b>AWS </b>

<h2>Lab Walk-through:</h2>

**Task 1: Identify Network Interfaces**
1. Go to EC2 in the AWS Management Console.
2. Select your "Server" instance.
3. Note the Server ENI (Elastic Network Interface) ID.
4. Repeat for the "Target" instance and note the Target ENI ID.

**Task 2: Configure Traffic Mirror Target**
1. Go to VPC in the AWS Management Console.
2. Under Traffic Mirroring, choose Mirror targets.
3. Create a new target with your Target ENI.

**Task 3: Configure Traffic Mirror Filter**
1. Under Traffic Mirroring in the navigation pane, select Mirror filters.
2. Create a filter to capture specific traffic, e.g., ICMP.
3. Add inbound rules as needed.

**Task 4: Configure Traffic Mirror Session**
1. Under Traffic Mirroring, choose Mirror sessions.
2. Create a session, specify source (Server ENI), target (MyTarget), and filter (MyFilter).

**Task 5: Capture and Verify Mirrored Traffic**
1. Use AWS System Manager Session Manager to connect to Client and Target instances.
2. On the Target instance, start tcpdump to capture traffic.
3. On the Client instance, initiate traffic, e.g., with a ping command.
4. Observe captured traffic on the Target instance.

**Task 6: Modify the Traffic Mirror Filter**
1. Initiate different traffic (e.g., HTTP) from the Client to the Server.
2. Modify the filter to capture the desired traffic.

**Task 7: Send Captured Traffic to a File**
1. Start tcpdump on the Target instance with the option to write captured packets to a file.
2. Generate traffic on the Client instance.
3. Stop tcpdump.
4. View the captured traffic file using tcpdump or tools like Wireshark.

**Conclusion:** You have successfully configured Traffic Mirroring for traffic monitoring.


<p align="center">
At the top of the AWS Management Console, in the search bar, search for and choose EC2 <br/>
<img src="https://imgur.com/R1WWmtX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the navigation pane at the left of the page, under Instances, choose Instances  <br/>
<img src="https://imgur.com/rr6UaGg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Choose the link for the Instance ID that is named Server. This opens the instance summary page for the Server EC2 instance <br/>
<img src="https://imgur.com/CyuJNFZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Scroll down in the Instance summary page. Locate and choose the Networking tab  <br/>
<img src="https://imgur.com/1rhiQw3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Scroll down and locate the Network Interfaces section. Copy the Interface ID and record it in you preferred text editor as the Server ENI. You need this ID in future tasks. This interface acts as the source of the mirroring traffic  <br/>
<img src="https://imgur.com/Y5eABR2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Repeat the previous steps to locate, view, and record the Interface ID for the EC2 Instance named Target. Record the ID as the Target ENI. This interface acts as the target of the mirroring traffic  <br/>
<img src="https://imgur.com/B3ptd0W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br />
<br />
At the top of the AWS Management Console, in the search bar, search for and choose VPC <br/> 
<img src="https://imgur.com/6bPxdYQ.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/> 
<br />
<br />
In the navigation pane at the left of the page, under Traffic Mirroring, choose Mirror targets, the Create traffic mirror target <br/> 
<img src="https://imgur.com/mhW2J4P.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Create a new target with your Target ENI <br/> 
<img src="https://imgur.com/NaRNmSM.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Under Traffic Mirroring in the navigation pane, select Mirror filters <br/> 
<img src="https://imgur.com/lIqk5wv.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Create a filter to capture specific traffic, e.g., ICMP <br/> 
<img src="https://imgur.com/qcf3bQD.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Add inbound rules as needed <br/> 
<img src="https://imgur.com/qcf3bQD.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Under Traffic Mirroring, choose Mirror sessions <br/> 
<img src="https://imgur.com/VtNXyG6.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Create a session, specify source (Server ENI), target (MyTarget), and filter (MyFilter) <br/> 
<img src="https://imgur.com/eX1quv0.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Use AWS System Manager Session Manager to connect to Client and Target instances <br/> 
<img src="https://imgur.com/Njw5rnI.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
On the Target instance, start tcpdump to capture traffic <br/> 
<img src="https://imgur.com/w2seZII.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
On the Client instance, initiate traffic, e.g., with a ping command <br/> 
<img src="https://imgur.com/aQ50t2R.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/>
<br />
<br />
Observe captured traffic on the Target instance <br/> 
<img src="https://imgur.com/hIlzHL3.png" height="80%" width="80%" alt="AWS Security Traffic Monitoring and Packet Analysis"/> 
</p> 
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
