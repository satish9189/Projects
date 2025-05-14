Ansible

Open spurce software provisioning and configuration management and application deployment tools enabling IaC.
Free automation tool that can automate IT tasks on local machine whete it is running or remote machine 

Benifits
Agentless
Open source
Avoid human errors
increase productivity
Secure (SSH)

Terminologies

control node or managed node
Server which runs ansible application

Modules
Modules is a command meant to be executed kn the client side

Task
A task is a section that consists of a single procedure to be completed. A task can have multiple modules

Playbook
Automation file with step by step execution of multiple tasks

YAML
A playbook written jn YAML

Inventory
File that has info about remote clients where tasks are executed

Tag 
A reference ot alias to a task

variable
Variables are like containers that hold the defined value which can be used repetitively

Role
Splitting of playbook into smaller groups. Role let you automatically load related vars, files, tasks, handlers, and other ansible artifacys based on known file structure.


Ansible works
Each specific  Task i ansible is written through a module

Multiple modules are written in sequential order 
Multiple modules for related tasks is called a play

All plays together  makes a playbook

Commands 
ansible-playbook example.yml

To run independently
ansible myservers -m ping

Ansible config files
/etc/ansible/ansible.cfg
/etc/ansible/hosts
/etc/ansible/roles

Automation tools
puppet and chef 
Ruby language, Requires agentst to be installed on clients 

Ansible 
agentless, well support and documentation, Easy installation 


Ansible  is an open source software
Ansible if free even though it owned by redhat
Ansible is same across all the platforms
The only difference is redhat provides additional product ansible tower and consulting or technical support for ansible

Ansible tower which is a GUI based tool to manage Ansible automation
Ansible tower is paid product 
Manages multiple ansible servers for large enterprise environment 

Ansible AWX
Open source
Free 
No support from redhat

Installing Ansible


