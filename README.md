🧑‍💻 Ansible Project – Automated Portfolio Deployment

This project automates the deployment of my personal DevOps portfolio using Ansible — making the setup consistent and repeatable across multiple servers.

🚀 What It Does

Configures Nginx web servers

Deploys static portfolio website files

Manages multi-server environments (Prod, Dev, Staging)

Integrates with Terraform for infrastructure provisioning
```mermaid
flowchart TB

A[Ansible Control Node] --> B[Inventory File<br>hosts.ini]
A --> C[Playbook<br>site.yml]

B --> D1[Dev Server]
B --> D2[Staging Server]
B --> D3[Production Server]

C --> D1
C --> D2
C --> D3

D1 --> E[Install Nginx + Deploy Files]
D2 --> E
D3 --> E

```

🧰 Tech Used

Ansible

Nginx

Ubuntu / AWS EC2

Terraform

⚙️ How to Run
1️⃣ Install Ansible

Run the following commands on your control node (local or EC2 instance):
--sudo apt update
--sudo apt install ansible -y

To verify installation:

ansible --version


Configure the Inventory (hosts) File

Create or edit your inventory file (for example: inventory/hosts.ini):

[webservers]
server1 ansible_host=3.142.52.119 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/your-key.pem
server2 ansible_host=xx.xx.xx.xx ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/your-key.pem
server3 ansible_host=xx.xx.xx.xx ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/your-key.pem


## ⚙️ How to Run
bash
ansible-playbook playbooks/site.yml 


