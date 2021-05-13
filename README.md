## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below:

https://drive.google.com/file/d/1dVTleQoboD9UE0RqC6Kpr0g1QqFJf4HZ/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YML file may be used to install only certain pieces of it, such as Filebeat.

config-elkstack-VM.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

Utilizing a load balancer enables high availability in case of DDoS attacks or general mishaps within any of the web servers.  Utilizing a jump box, enables a single point of entry to protect access to the network, and has the secondary effect of allowing the jump box to be used as a ansible server.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system configurations.
Filebeat watches changes to files.
Metricbeat watches system load and usage.

The configuration details of each machine may be found below.



| Name     | Function    | IP Address               | Operating System                       |
|----------|-------------|--------------------------|----------------------|
| Jumpbox  | Gateway     | 10.0.0.4  52.247.237.135 | Ubuntu 18.04         |
| Web-1    | DVWA Server | 10.0.0.5                 | Ubuntu 18.04         |
| Web-2    | DVWA Server | 10.0.0.6                 | Ubuntu 18.04         | 
| Web-3    | DVWA Server | 10.0.0.8                 | Ubuntu 18.04         |
| Elk-1660 | ELK Server  | 10.1.0.4                 | Ubuntu 18.04         |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 96.60.201.30

Machines within the network can only be accessed by the Jumpbox: 10.0.0.4.

A summary of the access policies in place can be found in the table below.

| NAME       | Public Access | Allowed IP addresses            |
|------------|---------------|---------------------------------|
| Jumpbox    | Yes           | SSH: 96.60.201.30               |
| Web-1      | No            | 10.0.0.4  Web: 96.60.201.30     |
| Web-2      | No            | 10.0.0.4  Web: 96.60.201.30     |
| Web-3      | No            | 10.0.0.4  Web: 96.60.201.30     |
| Elk Server | Yes           | ELK: 96.60.201.30 SSH:10.0.0.4  |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because of re-usability and ease of deployment creating the exact same configuration very simply.

The playbook implements the following tasks:
-Installs Docker.io
-Installs pip3
-Installs python Docker Module
-Increases Virtual Memory Defaults for Linux
-Downloads and launches the Elk Server inside the Docker Container


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.



### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5                 
10.0.0.6               
10.0.0.8                

We have installed the following Beats on these machines:
Filebeats: 
10.0.0.5
10.0.0.6
10.0.0.8
Metricbeats:
10.0.0.5
10.0.0.6
10.0.0.8

These Beats allow us to collect the following information from each machine:
File beats allows the administrator to monitor changes in files and access to files as well as logon events. Metric beats allows the administrator to monitor system load, CPU load, and Network load for each configured VM.


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the config-elkstack-VM.yml and config file to /etc/ansible/playbook
- Update the hosts file to include the IP address of the Elk Server under [elkservers]
- Run the playbook, and navigate to your Kibana URL to check that the installation worked as expected.

Commands to run playbook:
ansible-playbook config-elkstack-VM.yml
