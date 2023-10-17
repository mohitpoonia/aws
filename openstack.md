#### Installing OpenStack on Ubuntu 22.04 with DevStack
### What is Openstack
OpenStack is a free, open standard cloud computing platform. It is mostly deployed as infrastructure-as-a-service in public and private clouds where virtual servers and other resources are available to users.
**Devstack** DevStack is a set of Bash shell scripts that are used to create an OpenStack development environment. DevStack is built from the latest versions of everything from git master. It's designed for development and testing, and is not meant for production use.
DevStack is used to: 
- Prepare an environment for, configure, and deploy OpenStack
- Test and contribute to the OpenStack technologies themselves
- Understand the many OpenStack components and how to customize them
### Step 1: Update and Upgrade the System
```bash
sudo apt update
```
---
### Step 2: Create Stack user and assign sudo priviledge
```bash
sudo useradd -s /bin/bash -d /opt/stack -m stack
sudo chmod +x /opt/stack
```
---
### Step 3: Run the command below to assign sudo privileges to the user
```bash
echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack
```
---
### Step 4: Install git and download DevStack
```bash
su - stack
```
---
### Step 5:install Git by running the following command.
```bash
sudo apt install git -y
```
---
### Step 6:Using git, clone devstack’s git repository as shown.
```bash
git clone https://git.openstack.org/openstack-dev/devstack
```
---
### Step 7: Create devstack configuration file
```bash
cd devstack
```
---
### Step 8:create a local.conf configuration file
```bash
vim local.conf
```
---
### Step 9:Paste the following content
```bash
[[local|localrc]]
# Password for KeyStone, Database, RabbitMQ and Service
ADMIN_PASSWORD=lol
DATABASE_PASSWORD=lol
RABBIT_PASSWORD=lol
SERVICE_PASSWORD=lol
```
Save and exit the file[Press *Esc* then press :wq]
### Step 10: Install OpenStack with Devstack
```bash
./stack.sh
```
---

