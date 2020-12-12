## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

These files have been tested and used to generate a live ELK deployment on Azure. 
They can be used to either recreate the entire deployment pictured above. 
Alternatively, select portions of the ELK file may be used to install only certain pieces of it, such as Filebeat.

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly Reliable, in addition to restricting access to the network.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the fies and system metrics.
-Filebeat collects data about file logs.
-Metricbeat collects machine metrics.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.7   | Linux            |
| web-1    |Web Server| 10.0.0.8   | Linux            |
| Web-2    |Web Server| 10.0.0.9   | Linux            |
| Web-3    |Web Server| 10.0.0.10  | Linux            |
| ELK-1    |Elk Server| 10.1.0.4   | Linux            |

### Access Policies

-The machines on the internal network are not exposed to the public Internet. 
-Only the Jumpbox machine can accept connections from the Internet. 
-Access to this machine is only allowed from the admin Public ip address
-Machines within the network can only be accessed by Jumpbox.


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box  | Yes/No             | 10.0.0.7             |
| Web Server| No                 | 10.0.0.1             |
| ELK Server| No                 | 10.0.0.1             |
| Kibana    | Yes                | Public IP            |
| DVWA      | Yes                | Public IP            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. 
-No configuration was performed manually, which is advantageous because its setup is within minutes using OpenSSH. 
-There is also no need to install applications on the servers.  


The playbook implements the following tasks:

-Install Docker.io
-Increase Virtual Memory
-Download and Launch ELK Docker Container
-Make published ports available. 


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
| Web Server| No                 | 10.0.0.1             |
| Jump Box  | Yes/No             | 10.0.0.7             |

We have installed the following Beats on these machines:
| ELK Server| No                 | 10.0.0.1             |
| Kibana    | Yes                | Public IP            |
| DVWA      | Yes                | Public IP            |

These Beats allow us to collect the following information from each machine:
Filebeat collects log data
Metricbeat collects metrics from the operating system and from services running on the server
Packetbeat collects packets sent to and from the server

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Instal-Elk.yml file to /etc/ansible.
- Update the host file to include...
- Run the playbook, and navigate to Ansible to check that the installation worked as expected.

Move my-playbook.yml to ansible/playbooks
To switch the machine the playbook is running on you edit my-playbook.yml. One line of code will decide where ansible is installed and another will choose where it runs
The Public IP that is hosting the machine from Azure
