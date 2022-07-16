# Project1
Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
Note: The following image link needs to be updated. Replace diagram_filename.png with the name of your diagram image file.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Diagram file may be used to install only certain pieces of it, such as Filebeat.

TODO: Enter the playbook file.

This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration

Beats in Use
Machines Being Monitored


How to Use the Ansible Build


Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly _functional, in addition to restricting high traffic to the network.

What aspect of security do load balancers protect? What is the advantage of a jump box?
The load balancers prevent traffic from overlading severs by rerouting traffic to different servers. This helps prevent single point attacks.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and systemlogs.

Filebeat monitors log files and is able to be searched through elasticsearch/logstach.
Metricbeat records metrics and statistics and can be reviewed through elasticsearch/logstach.

The configuration details of each machine may be found below.
Note: Use the Markdown Table Generator to add/remove values from the table.



Name :Jump-Box-Provisioner	
Function: Gateway
IP Address 10.0.0.4
Operating System Linux

Name:ELKVM 
Function: Server
IP Address: 10.1.0.11
Operating System: Linux

Name: VM1
Gateway: Server
IP Address:10.1.0.13
Operating System: Linux

Name:VM2
Gateway:Server
IP Address:10.1.0.14
Operating System:Linux




Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the jumpboxprovisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

TODO: Add whitelisted IP addresses

Machines within the network can only be accessed by my local IP address

TODO: Which machine did you allow to access your ELK VM? What was its IP address?
The jumpboxprovisioner allowed access to the ELK VM. The IP address is 10.0.04
A summary of the access policies in place can be found in the table below.



Name: Jump-Box-Provisioner
Publicly Accessible yes
Allowed IP Addresses public ip

Name ELK-VM 
Publicly Accessible: No
Allowed IP Address:10.0.0.4

Name: VM 1 
Publicly Accessible: No
Allowed IP Address: 10.0.04

Name VM 2 
Publicly Accesible: No
Allowed IP Address: 10.0.0.4





Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

 What is the main advantage of automating configuration with Ansible?
 With ansible you are able to use yml playbooks for configuration managenment as well as automation.

The playbook implements the following tasks:

TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
Open terminal and SSH into the jump-box-provisioner
Install docker with command sudo docker start tender_morse and sudo docker attach tender_morse
Command directory to the roles directory, /etc/ansible/roles, and create the ELK playbook.
SSH into the ELK virtual machine. 



Target Machines & Beats
This ELK server is configured to monitor the following machines:

IP Addresses of machines monitored: VM-1 10.1.0.13, VM-2 10.1.0.14


We have installed the following Beats on these machines:
Filebeat and Metricbeat are installed

These Beats allow us to collect the following information from each machine:

Beats:
Filebeat collects log files from the remote machine and monitors the data. 
Metricbeat collects the machine information such as the operating system and outputs the data.

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the file to _/etc/ansible/roles/files____.
Update the __filebeat-configuration.yml___ file to include the ELK private ip in line 62 and 96.
Run the playbook, and navigate to http://20.49.3.56.5601 to check that the installation worked as expected.

Copy the file to _/etc/ansible/roles/files____.
Update the _metricbeat-configuration.yml___ file to include the ELK private ip.
Run the playbook, and navigate to http://20.49.3.56.5601 to check that the installation worked as expected.


 Answer the following questions to fill in the blanks:

Which file is the playbook? Where do you copy it? The file is filebeat-playbook.yml and can be found in /etc/ansible/roles
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? 
_Which URL do you navigate to in order to check that the ELK server is running?
http://20.49.3.56:5601
As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.
