# Azure-ELK-Stack
An Azure deployment of web servers and a logging server using Docker and Ansible

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files were used to deploy a live ELK deployment on Azure containing two web servers, a jumpbox provisioner, and a logging server. These files can be used to replicate the deployment depicted above, and can be easily modified to deploy additional logging services or additional web server content.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the Damn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, while the jump box ensures there is only a single means of access to the internal network via a secure shell.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for filesystem changes and suspicious modifications as well as system and network modifications using Filebeat and Metricbeat.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name          | Function       | IP Address |
|---------------|----------------|------------|
| Jump Box      | ssh Gateway    | 10.0.0.4   |
| Web-1         | Web Server     | 10.0.0.5   |
| Web-2         | Web Server     | 10.0.0.6   |
| ELK Logger    | Logging Server | 10.1.0.4   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the web servers (via the Azure-managed load balancer) and the ELK server accept external HTTP connections. These machines only accept connections from a whitelist of IP addresses containing only those IPs associated with personal workstations; these will not be shared in this repository for privacy reasons. The web servers only allow http traffic on port 80, and the logging server only accepts http traffic on port 5601 (used to access the Kibana web app).

Machines within the network can only be accessed by the Jump Box machine via ssh. The ssh protocol uses public/private key authentication, with one key pair used for logging into the jump box from a workstation (private key on workstation, public key on jump box) and one other key pair used for logging into each of the other VMs from the jump box (private key on jump box, public key on each other VM).

A summary of the access policies in place can be found in the table below.

| Name       | Public Access | Whitelisted IP address(es) | Protocol |
|------------|---------------|----------------------------|----------|
| Jump Box   | Yes           | x.x.x.x (workstation)      | ssh      |
| Web-1      | No            | 10.0.0.4                   | ssh      |
| Web-2      | No            | 10.0.0.4                   | ssh      |
| ELK Logger | No            | 10.0.0.4                   | ssh      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. This allows all configurations to be performed in batch without ever needing to log into the ELK machine itself. This is a highly modular design that can be easily configured for a variety of applications and deployed quickly across as many VMs as necessary.

The playbook implements the following tasks:
- 
- 
- 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 at 10.0.0.5
- Web-2 at 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat collects logs of file access and modification, including data about which user modified the file and what process modified that file.
- Metricbeat collects logs of system configuration changes, including starting and stopping of processes, installation of new processes, and resource usage (RAM, CPU, Disk I/O, etc.)

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
