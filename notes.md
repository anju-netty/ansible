##  Install ansible on mac?
```bash
sudo pip install ansible
```


## Check version of ansible and see if its installed properly

```bash
ansible --version
```
output:
```
ansible 2.9.5
  config file = None
  configured module search path = ['/Users/anju/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/ansible
  executable location = /Library/Frameworks/Python.framework/Versions/3.7/bin/ansible
  python version = 3.7.2 (v3.7.2:9a3ffc0492, Dec 24 2018, 02:44:43) [Clang 6.0 (clang-600.0.57)]
  ```

  ## Check ansible playbook version

  ```bash
  ansible-playbook --version
  ```

  ```
  ansible-playbook 2.9.5
  config file = None
  configured module search path = ['/Users/anju/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/ansible
  executable location = /Library/Frameworks/Python.framework/Versions/3.7/bin/ansible-playbook
  python version = 3.7.2 (v3.7.2:9a3ffc0492, Dec 24 2018, 02:44:43) [Clang 6.0 (clang-600.0.57)]
  ```

  ## Uninstall ansible

  sudo pip uninstall ansible

```
   /Library/Frameworks/Python.framework/Versions/3.7/lib/python3.7/site-packages/ansible_test/*
Proceed (y/n)? y
  Successfully uninstalled ansible-2.9.5

```
## SSH connection to the remote hosts

 ```
  passwordless login using public private key pair

Run commands to generate public key:                Run commands to install ssh server:
ls -al ~/.ssh/id_*.pub                              sudo apt install openssh-server
ssh-keygen -t -rsa -b 4096                          Sudo systemctl status | grep 'ssh'
                                                    sudo systemctl status ssh.service
                                                    sudo ufw allow-ssh-+
 +------+                                           +------+
 |      |                                           |      |
 |      |ssh-copy-id username@192.168.0.18                 |
 |      +------------------------------------------>+      |
 |      |         [copy of public key of client]    |      |
 |      |                                           |      |
 +------+                                           +------+

 client                                              ssh Server - 192.168.0.18
 private key
 public key


```

##Create host file

mkdir /etc/ansible
cd /etc/ansible
sudo nano hosts
[ctrl + X] Press 'Y'

sudo nano ansible.cfg
[default]
remote_user = netty
[ctrl + X] Press 'Y'

```bash
ansible all --list-hosts
  hosts (1):
    192.168.0.19

ansible all --list-hosts
  hosts (1):
    192.168.0.19

ansible all -m ping
192.168.0.19 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```
- hosts: apache
  tasks:
    - name: install apache2
      apt: name=apache2 update_cache=yes state=latest