<h1>SOAR-EDR Project</h1>

<h2>Description/Objectives</h2>
- Build a custom detection/response(DR) rule in Lima Charlie(EDR) that will detect the use of a password recovery tool that will be executed on a designated cloud virtual machine.
- Then the information from the Lima Charlie detection will be sent to Tines(SOAR). A custom playbook will be created in Tines.
- The custom playbook created in Tines will then send the user(myself) an email, and a Slack message containing the details of the detection.
- Finally, a prompt will be generated on Tines asking the user if they want to isolate the designated machine.
- If the user selects "yes" for the prompt, Lima Charlie will isolate the machine automatically. 
