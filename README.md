# laughing-eureka
Project-1 Files
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the  file may be used to install only certain pieces of it, such as Filebeat.

  - install-elk.yml
  - filebeat-playbook.yml
  - metricbeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly [available], in addition to [restricting access] to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the [log files] and [system metrics.]
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function | IP Address | Operating System     |
|------------|----------|------------|----------------------|
| Jumpbox    | Gateway  | 10.0.0.4   | Linux (Ubuntu 18.04) |
| Web-1      | DVWA     | 10.0.0.7   | Linux (Ubuntu 18.04) |
| Web-2      | DVWA     | 10.0.0.8   | Linux (Ubuntu 18.04) |
| Web-3      | DVWA     | 10.0.0.9   | Linux (Ubuntu 18.04) |
| Project-VM | Elk      | 10.1.0.4   | Linux (Ubuntu 18.04) |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the [Jumpbox] machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
-[Public IP of personal device]

Machines within the network can only be accessed by [Jumpbox].
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name       | Public Accessible | Allowed IP Addresses |
|------------|-------------------|----------------------|
| Jumpbox    | Yes               | Local IP Address     |
| Web-1      | No                | 10.0.0.4             |
| Web-2      | No                | 10.0.0.4             |
| Web-3      | No                | 10.0.0.4             |
| Project-VM | Yes               | Local IP Address     |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because [configurations can be done across multiple servers at once with Ansible.] 
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
  - Install Docker
  - Install python3-pip
  - Install Docker module
  - Increase virtual memory
  - Download and install Docker ELK container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.7
- 10.0.0.8
- 10.0.0.9
We have installed the following Beats on these machines:
- Filebeats
- Metricbeats

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
- Filebeats collects information about changes to specific logs and files. Metricbeats collects information about the virutal system such as CPU and memory. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the install-elk.yml, filebeat-playbook.yml, and metricbeat-playbook.yml to your ansible container.
- Update the ansible hosts file to include the IP addresses of the machine(s) that will have ELK installed.
- Run the playbook, and navigate to http://[Project-VM IP]:5601/app/kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._