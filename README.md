## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Diagram](https://github.com/mlinarte25/ELK-Project/blob/master/Images/Screen%20Shot%202020-04-21%20at%209.40.15%20PM.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ![Filebeat-playbook](https://github.com/mlinarte25/ELK-Project/blob/master/filebeat-playbook.yml) file may be used to install only certain pieces of it, such as Filebeat.


This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure defending against distributed DDoS attacks, in addition to restricting traffic to the network.
A load balancer is a device that acts as a reverse proxy and distributes network or application traffic across a number of servers. Load balancers are used to increase capacity (concurrent users) and reliability of applications.

A jumpbox is a system on a network used to access and manage devices in a separate security zone. A jump server is a hardened and monitored device that spans two dissimilar security zones and provides a controlled means of access between them.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
Metricbeat collect metrics from the operating system and from services running on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| DVWA-V1  | Load Ba. | 10.1.0.5   | Linux            |
| ElkServer|          | 10.1.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 10.1.0.4 and 137.135.51.247

Machines within the network can only be accessed by SSH.
I allowed access from my DVWA-V1 to my ELKServer VM--10.1.0.6

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses  |
|----------|---------------------|-----------------------|
| Jump Box | Yes                 |10.1.0.4 home networkIP|    
| DVWA-V1  | No                  |10.1.0.5               |
|ElkServer | Yes                 |10.0.0.6 home networkIP |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because its freem very simple to set up and use. It is powerful, flexible and efficient; allowing you to not need IT support.

The playbook implements the following tasks:
- Install docker and start and attach your container
- 
- 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![docker ps](https://github.com/mlinarte25/ELK-Project/blob/master/Images/Docker%20ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.1.0.6

We have installed the following Beats on these machines:
- Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing in this case we were able to see data logs on kibana.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Filebeat configuration file from Ansible container to your ElkServer VM.
- Update the configuration file to include private IP of elkserver 10.1.0.6
- Run the playbook, and navigate to curl to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- The playbook is /etc/ansible/roles/elkserver-playbook.yml and copied to the ansible directory.
- Update /etc/ansible/filebeat-configuration.yml and you include the machine's IP to it.
How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- 
http://104.42.13.125:5601/ this is the url to reach kibana.
