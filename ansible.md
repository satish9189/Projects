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

****Script****

#!/bin/bash

# To verify whether pip is already installed for your preferred Python

python3 -m pip -V   

# If you see an error like No module named pip, you will need to install pip under your chosen Python interpreter before proceeding. This may mean installing an additional OS package (for example, python3-pip), or installing the latest pip directly from the Python Packaging Authority by running the following:

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user

Installing Ansible

# Use pip in your selected Python environment to install the full Ansible package for the current user

python3 -m pip install --user ansible

# You can install the minimal ansible-core package for the current user

python3 -m pip install --user ansible-core

# Alternately, you can install a specific version of ansible-core

python3 -m pip install --user ansible-core==2.12.3


Upgrading Ansible
# To upgrade an existing Ansible installation in this Python environment to the latest released version, simply add --upgrade to the command above

python3 -m pip install --upgrade --user ansible


# NOTE If  SElinux enabled on remote nodes we also need to install libselinux-python package

All tasks are executed sequential
Each task processed one at a time
Indentation extremly important
No tabs in yaml file
onlu use spaces
Empty lines have no values
File extension is usually .yml or .yaml

No difference in double quotes or no quotes for task name


Sample YAML

name: sampleplaybook # Playbook name
hosts: all or localhost # Where to run
become: yes # Run as a different user
become_user: root

tasks:
- name: Install apache
  yum:  # run task module
  name: httpd # Package name
  state: present # What to do install
- name: Second sample task
  service:
  name: httpd
  state: started

Sample Playbook

name: "first playbook"
hosts: all
tasks: 
- name: "Test Connectivity"
- ping:

Check Syntax of playbook

ansible-playbook --syntax-check playbookname.yml # To do dry run
ansible-playbook --check playbookname.yml
ansible-playbook PathToplaybookname.yml # Run the playbook

running ansible without playbook
ansible

running ansible with playbook
ansible-playbook

  
  


