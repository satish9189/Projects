
# 📘 Ansible Guide

## 🛠️ What is Ansible?

```text
Open source software provisioning, configuration management, and application deployment tool enabling Infrastructure as Code (IaC).
A free automation tool that can automate IT tasks on local or remote machines.
```

---

## ✅ Benefits

```text
- Agentless
- Open source
- Avoids human errors
- Increases productivity
- Secure (uses SSH)
```

---

## 📌 Key Terminologies

- **Control Node / Managed Node**  
  Server which runs the Ansible application

- **Modules**  
  A module is a command meant to be executed on the client side

- **Task**  
  A task is a section that consists of a single procedure to be completed. A task can include multiple modules

- **Playbook**  
  Automation file with step-by-step execution of multiple tasks

- **YAML**  
  Playbooks are written in YAML syntax

- **Inventory**  
  File that has information about remote clients where tasks are executed

- **Tag**  
  A reference or alias to a task

- **Variables**  
  Containers that hold defined values which can be reused

- **Role**  
  Splitting of playbooks into smaller groups. Roles let you automatically load related variables, files, tasks, handlers, and other Ansible artifacts based on a known file structure.

---

## ⚙️ How Ansible Works

- Each specific task is written using a module  
- Multiple modules are written in sequential order  
- A group of related modules forms a **Play**  
- All plays together form a **Playbook**

---

## 💻 Useful Commands

```bash
ansible-playbook example.yml         # Run a playbook

ansible myservers -m ping            # Run a module independently
```

---

## 📂 Important Ansible Configuration Files

```text
/etc/ansible/ansible.cfg     # Main Ansible configuration file
/etc/ansible/hosts           # Inventory file for hosts
/etc/ansible/roles           # Directory for roles
```

---

## 🧰 Other Automation Tools

- **Puppet and Chef**  
  - Based on Ruby  
  - Requires agents on client machines  

- **Ansible**  
  - Agentless  
  - Easy installation  
  - Excellent documentation and support

---

## 🏢 Ansible Ecosystem

- **Ansible**
  - Open source
  - Free to use (owned by Red Hat)
  - Same across platforms

- **Ansible Tower**
  - GUI-based tool to manage Ansible automation
  - Paid product from Red Hat
  - Used for large enterprise environments

- **Ansible AWX**
  - Open source version of Ansible Tower
  - Free to use
  - No official Red Hat support

---

## 📥 Installing Ansible

### Script

```bash
#!/bin/bash

# Check if pip is installed
python3 -m pip -V   

# If pip is not installed
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --user

# Install Ansible
python3 -m pip install --user ansible

# OR install minimal version
python3 -m pip install --user ansible-core

# OR install specific version
python3 -m pip install --user ansible-core==2.12.3

# Upgrade Ansible
python3 -m pip install --upgrade --user ansible
```

> 📌 If SELinux is enabled on remote nodes, install the `libselinux-python` package.

---

## ⚠️ YAML Essentials

- All tasks are executed sequentially
- Indentation is extremely important
- **Do not use tabs**, only use spaces
- Empty lines have no value
- File extension should be `.yml` or `.yaml`
- Quotes around task names are optional

---

## 📄 Sample YAML

```yaml
name: sampleplaybook  # Playbook name
hosts: all            # Where to run
become: yes           # Run as a different user
become_user: root

tasks:
  - name: Install Apache
    yum:
      name: httpd
      state: present

  - name: Start Apache service
    service:
      name: httpd
      state: started
```

---

## 📝 Sample Playbook

```yaml
name: "First Playbook"
hosts: all
tasks: 
  - name: "Test Connectivity"
    ping:
```

---

## 🔍 Syntax & Playbook Execution

```bash
ansible-playbook --syntax-check playbook.yml   # Check syntax
ansible-playbook --check playbook.yml          # Dry run
ansible-playbook path/to/playbook.yml          # Run playbook

ansible             # Run Ansible without playbook
ansible-playbook    # Run Ansible with playbook
```
