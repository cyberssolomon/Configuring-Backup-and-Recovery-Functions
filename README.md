<h1>Configuring Backup and Recovery Functions</h1>

<h2>Tools and Software Used</h2>

- <b>Windows Server Backup (GPMC)</b> 
- <b>pfSense</b>
- <b>Wbadmin</b> 
- <b>NFS </b>
- <b>Vi Editor </b>

 

<h2>Environments Used </h2>

- <b>DomainController01 (Windows: Server 2019)</b> 
- <b>StorageServer01 (Linux)
- <b>pfSense-dc (FreeBSD:pfSense)</b>
- <b>WebServer01 (Linux) (</b>
- <b>WebServer02 (Linux)</b>



 
<h2>Description</h2>
Project consists of configuring backup and recovery functions that support business continuity, disaster recovery, and high availability: installing and configuring the Windows Server Backup server feature, and restoring the Windows server from a System State Backup.
<br />

### Section 1

<h2>Install Windows Server Backup:</h2>








<p align="center">
Show the completed Windows Server Backup feature installation: <br/>
<img src="https://i.imgur.com/JjLOKmg.png" height="80%" width="80%" alt="Section 1 Steps"/>

 <h2>Configure a System State Backup:</h2>







<p align="center">
Show the Scheduled Backup settings, including the destination and backup time: <br/>
<img src="https://i.imgur.com/AREuItx.png" height="80%" width="80%" alt="Section 1 Steps"/>

 <h2>Restore from a System State Backup:</h2>







<p align="center">
Show the Recovery Wizard Confirmation page: <br/>
<img src="https://i.imgur.com/81cz1Nk.png" height="80%" width="80%" alt="Section 1 Steps"/>













 ### Section 2

<h2>Configure an NFS Share:</h2>










<p align="center">
Show the results of the reverse DNS query: <br/>
<img src="https://i.imgur.com/1Zl1pWv.png" height="80%" width="80%" alt="Section 2 Steps"/>
<br />
<br />
Show the updated webserver01 home page:  <br/>
<img src="https://i.imgur.com/YzZD5Mn.png" height="80%" width="80%" alt="Section 2 Steps"/>
<br />
<br />
Show the updated webserver02 home page: <br/>
<img src="" height="80%" width="80%" alt="Section 2 Steps"/>


 <h2>Configure Load Balancing:</h2>










<p align="center">
Show the http_server_pool backend: <br/>
<img src="" height="80%" width="80%" alt="Section 2 Steps"/>
<br />
<br />
Show the http_access frontend: <br/>
<img src="" height="80%" width="80%" alt="Section 2 Steps"/>
<br />
<br />
Show the new Host Overrides entry for cscd.securelabsondemand.com: <br/>
<img src="" height="80%" width="80%" alt="Section 2 Steps"/>


<h2>Verify Load Balancing:</h2>










<p align="center">
Show the result of the DNS query for cscd.securelabsondemand.com: <br/>
<img src="" height="80%" width="80%" alt="Section 2 Steps"/>
<br />
<br />
Show the Statistics Report with a value of at least 1 in the Sessions > Total column of the http_server_pool_ipvANY box, for both webserver01 and webserver02: <br/>
<img src="" height="80%" width="80%" alt="Section 2 Steps"/>









 ### Section 3

<h2>Add Failover Functionality:</h2>










<p align="center">
Show the updated Check Frequency value in the Health checking module: <br/>
<img src="" height="80%" width="80%" alt="Section 3 Steps"/>



 <h2>Validate Failover Functionality:</h2>










<p align="center">
Show the HAProxy Statistics Report with a host in a DOWN state, as well as the UP host having more total sessions (http_server_pool_ipvANY, Sessions> Total) than the DOWN host: <br/>
<img src="" height="80%" width="80%" alt="Section 3 Steps"/>



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
