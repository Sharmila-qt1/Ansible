### installing ansible
* create two instances
* one is for ansible master
* one is for ansible node
## In master install ansible and python
---
 'sudo apt update'
 'sudo apt install software-properties-common'
 'sudo add-apt-repository --yes --update ppa:ansible/ansible'
 'sudo apt install ansible -y'
 'ansible --version'
---
---
 python3 --version
 pip3 --version
 python3 -m pip install --user ansible
---
---
 sudo nano /etc/ssh/sshd_config
# Change PasswordAuthentication to yes
 sudo systemctl restart sshd
---
![preview](image.png)
* create user "jenkins" in two nodes same user and password for better configuration
* Lets make jenkins administrator
---
sudo visudo
---
![preview](image.png)
![preview](image.png)
# Ansible Setup with Key Based Authentication between ACN and Node
* Overview
* Create two linux vm’s
* Create a user on both vms with password
* Ensure the user has sudo permissions
* Now create an ssh key pair on Ansible control node

# in node
* after creating user "jenkins"
* do password authentication
* give sudoers permission
* copy private ip of node and configure it in master
* in master: "ssh-copy-id ssh jenkins@privateip"
![preview](image.png)
![preview](image.png)
![preview](image.png)
![preview](image.png)
* exit from  node user in master
* login to the user in master
* do "ssh-keygen"
* now 'copy ssh copy id"
* create one file
* "vi inventory"
* in that inventory file give ==> private ip of node
* now run "ansible -i inventory -m ping all"
---------installation completed---------------------

