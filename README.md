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
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
