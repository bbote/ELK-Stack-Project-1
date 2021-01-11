## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the RedTeam file may be used to install only certain pieces of it, such as Filebeat.

  -[elk.yml](https://github.com/bbote/ELK-Stack-Project./blob/main/Ansible/elk.yml)
  

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting high traffic to the network.
- What aspect of security do load balancers protect? - They defend and organisations from DDos attacks, by shifting attacks from the corporate server to a public cloud provider. They are less costly as well as more efficient to manange and maintian than hardware defencses such as perimeter firewalls.

- What is the advantage of a jump box? They provide and gateway to a private network which minimizes the attack surface making it harder to launcvh an attack.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the network and system logs.
- What does Filebeat watch for? It monitors file changes and locations then forward the data to Elasticserach/Losgtash or indexing.
  
- What does Metricbeat record? It keeps a record of statics/metics before sending the to Elasticserach/Losgtash 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.8 | Linux            |
| Web-1     | DVWA Web Server          | 10.0.0.9           |                  |
| Web-2     | DVWA Web Server     | 10.0.0.9           |                  |
| Web-4     | DVWA Web Server         | 10.0.0.4            |                   |
| Web-3     | Elk Server         | 10.1.0.4           |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 20.37.245.72

Machines within the network can only be accessed by eachother.
- Which machine did you allow to access your ELK VM? The Web-1,Web-2,Web-4 VM's send traffic to the Web-3 which is Elk Server.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes              | 23.37.245.72    |
| Web-1     | No               | 10.0.0.0/23             |
| Web-2     | No               | 10.0.0.0/23             |
| Web-4     | No               | 10.0.0.0/23             |
| Web-3 (Elk Server)     | No               | 10.0.0.0/023 172.198.225.210:5601            |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

- Manual configuration is prone to human error, therefore it is the best alternative for configuration.
- It is also able to automate complex multi-tier IT application environments.

The playbook implements the following tasks:
- Install Docker : the Docker engine, used for running containers
- Install pip3: Package used to install Python software
- Install Docker module: Python client for Docker
- Increase virtual memory for the ELK container
- Download and launch Docker-ELK container with port mapping set to
  - 5601:5601
  - 9200:9200
  - 5044:5044


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![alt text here](https://github.com/bbote/ELK-Stack-Project./raw/main/Diagrams/ELK-VM%20Docker%20PS..png)

![alt text here](https://github.com/bbote/ELK-Stack-Project./raw/main/Diagrams/ELK-VM%20Docker%20Dashboard.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
