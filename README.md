<h1>SOAR-EDR Project</h1>

<h2>Description/Objectives</h2>
- Build a custom Detection/Response(DR) rule in Lima Charlie(EDR) that will detect the use of a password recovery tool that will be executed on a designated cloud virtual machine.
<br>
- Then the information from the Lima Charlie detection will be sent to Tines(SOAR). A custom playbook will be created in Tines.
<br>
- The custom playbook created in Tines will then send the user an email, and a Slack message containing the details of the detection.
<br>
- Finally, a prompt will be generated on Tines asking the user if they want to isolate the designated machine.
<br>
- If the user selects "yes" for the prompt, Lima Charlie will isolate the machine automatically. 
<br>
- If the user selects "no" for the prompt then a message will be sent to Slack saying the computer has not been isolated and the incident needs to be investigated.  

<h2>Utilities Used</h2>

- <b>Draw.io</b>
- <b>Lima Charlie (EDR Solution)</b>
- <b>Tines (SOAR Solution)</b>
- <b>Slack</b>
- <b>Cloud VM</b>
- <b>Powershell</b>
- <b>LaZagne.exe<b>

<h2>Environments Used </h2>

- <b>Lima Charlie</b>
- <b>Tines</b>
- <b>Slack</b>
- <b>MS Server 2022</b>

<h2>Project walk-through:</h2>

<p align="left">
Created a workflow diagram in Draw.io to demonstrate the objectives of the project: <br/>
<img src="https://imgur.com/TLMH96Z.png" height="80%" width="80%" alt="Draw.io Workflow Diagram"/>
<br />
<br />
<br />
Installed the Lima Charlie agent on the cloud VM and the VM is displayed as an end node in the Lima Charlie sensors list. 
<img src="https://imgur.com/9z2AxHv.png" height="80%" width="80%" alt="Lima Charlie Agent Install"/>
<br />
<br />
<br />
Created a Detection/Response(DR) rule within Lima Charlie to detect when the password recovery tool is run on the virtual machine.
<img src="https://imgur.com/usPq9dg.png" height="80%" width="80%" alt="Detection Response Rule"/>
<br />
<br />
<br />
Made a Slack alert channel. This will eventually be connected to the Tines playbook.
<img src="https://imgur.com/hcZJbj3.png" height="80%" width="80%" alt="Slack Alert Channel"/>
<br />
<br />
<br />
Created the Tines Playbook to have automation take place.
  - Connected the Tines Playbook to Lima Charlie through the webhook.
  <br />
  - Add actions to the webhook for sending a message to Slack and sending the user an email.
  <br />
  - Add "yes" and "no" triggers
  <br />
  - Add a Slack message action to the "no" trigger. This will send a message to Slack urging the user to investigate the incident if the client is not isolated.
  <br />
  - Add two Lima Charlie sensors to the "yes" trigger. This will isolate the machine, get its isolation status, and send all of this information to a message in Slack.
  <br />
<img src="https://imgur.com/3XXoPYc.png" height="80%" width="80%" alt="Tines Playbook Creation"/>
<br />
<br />
<br /> 
After the Tines playbook creation, the password recovery tool (LaZagne.exe) is run on the Windows Server VM. This executable is trying to recover passwords on the system. 
For the sake of security, the content of this executable was not displayed. 
<img src="https://imgur.com/Y68WYRI.png" height="80%" width="80%" alt="LaZagne.exe is ran on VM"/>
<br />
<br />
<br />
Lima Charlie detects the executable being run on the virtual machine. 
<img src="https://imgur.com/Feyx9cH.png" height="80%" width="80%" alt="Lima Charlie detects the executable"/>


