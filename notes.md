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
  