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
