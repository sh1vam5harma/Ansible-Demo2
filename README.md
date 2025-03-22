Part 1. Executed in a red hat enterprise linux sandbox using ansible-navigator which is included in the Ansible Automation Platform and leverages the CLI. 

Background: ansible-navigator is a textual user interface (TUI) which could function as a replacement for the ansible-playbook utility. It integrates with VSCode. ansible-navigator.yml is the name of the config file present in each project that will determine how automation is created and executed with ansible-navigator. 

Project: writing a test yaml file to ping the localhost, essentially telling your system to check if it can connect to the itself (localhost) using the ping command. Run the playbook using: ansible-navigator run ./test.yml -m stdout 

This will display the output directly in the terminal (standard output).  


Part 2. Does not contain any code. Is an introduction to Ansible automation controller (part of the web-based UI interface for Red Hat Ansible Automation Platform). Allows you to run your playbooks without using the command line. 

The lab: Created an inventory to manage servers, import your playbooks into Projects, add Job Templates to run playbooks, and create a Workflow to link the playbooks. 

Notes: Projects are logical groups of Ansible playbooks. The playbooks usually reside in source code version control system like Git (Github or Gitlab). With Projects, we can reference a repository or directory. An inventory is a collection of hosts against which jobs (playbooks) can run against- it indicates which nodes will be managed by the control machine. 


Part 3. DevOps & Cl/CD (has no files associated with it)

The lab: using Automation Controller, integrate a CI/CD pipeline into an Automation Controller to see how the Red Hat Ansible Automation Platform supports DevOps practices. Then, integrate Jenkins into the automation controller, configure a web server, and deploy a web application. Use the controller Approval to allow final checks before deploying to Prod. Use Gitea for source code management and initiate webhooks that automatically make HTTP POST requests to a server when certain Gitea events trigger. Gitea has a webhook configured to initiate a Jenkins job when new code is committed to the repository. Integrate Jenkins into the automation controller using the API. Integrate Jenkins into the Automation Controller using a Job Template. Use Jenkins to run development tasks and checks before handing over the code to operations for deployment. 

Steps:
Pull the latest application code from the Gitea repo and install the packages needed to test the application. Update the application in VSCode and trigger the Gitea webhook- the Gitea webhook starts the pipeline in Jenkins. 
Jenkins triggers the build. 
Use Red Hat’s Automation Controller to approve and deploy the application. 
