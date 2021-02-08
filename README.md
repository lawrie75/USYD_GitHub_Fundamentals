# GitHub-Fundamentals
github homework week 13

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO:(https://github.com/lawrie75/USYD_GitHub_Fundamentals/blob/main/3-Diagrams/ElkServer_Diagram.drawio.pdf)]

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the *playbook* file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._ *https://github.com/lawrie75/USYD_GitHub_Fundamentals/blob/main/1-ansible/filebeat-playbook.yml*

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly *efficient*, in addition to restricting *access* to the network.
- _TODO: What aspect of security do load balancers protect? *Layer 4 Transport* What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box |  Gateway |  10.1.0.4  |       Linux      |
| Web-1    | Web site |  10.1.0.5  |       Linux      |
| Web-2    | Web site |  10.1.0.6  |       Linux      |
| Web-3    | Web site |  10.1.0.7  |       Linux      |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the *Jump Box* machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_. *119.18.0.55*

Machines within the network can only be accessed by *Jump Box*.
- _TODO: Which machine did you allow to access your ELK VM?*Jump Box* What was its IP address?_*10.1.0.4*

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ *For efficient and precise configuration setup*

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...*Configure Elk virtual machine with docker*
- ...*Install docker.io*
- ...*Install pip3*
- ...*Install Docker python module*
- ...*Use more  memery*
- ...*download and launch a docker elk container*

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
*Web1 10.1.0.5* 
*Web2 10.1.0.6* 
*Web3 10.1.0.7*

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
*Filebeat and Metricbeat*

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
*file beat collect data such as log files, events and locations (https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-overview.html).*
*Metricbeat collects data from a service to create statistical data from the captured info*

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _filebeat-playbook.yml_ file to _root@ac31fe7f9443:/etc/ansible#_.
- Update the *pentest.yml* file to include...
- Run the playbook, and navigate to _DVWA_ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? *filebeat-playbook and metricbeat-playbook* 
Where do you copy it?*/etc/ansible*
?- *Which file do you update to make Ansible run the playbook on a specific machine? *pentest.yml*
How do I specify which machine to install the ELK server on versus which to install Filebeat on?_in the config files for both filebeat and metricbeat*
- _Which URL do you navigate to in order to check that the ELK server is running? *10.0.0.4:5601 (kibana)*

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
