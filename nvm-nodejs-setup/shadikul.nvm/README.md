# Automated NVM Installation on Ubuntu Using Ansible

## Configuration
Modify the variable values in **defaults/main.yml** as needed to specify the desired NVM version, Node.js version, and other relevant settings.

## Install NVM and Node.js
To execute the playbook, navigate to the project root directory and run the following command:
```
ansible-playbook -i inventory.ini playbook.yml
```
- To ensure that the newly updated settings, such as sourcing NVM, take effect immediately, apply the changes to your shell environment by running the following command after logging into the server via SSH:
```
source ~/.profile
```

## Uninstalling NVM
To completely remove NVM from your system, follow these steps:

- Run the following command to delete the NVM directory:
```
sudo rm -rf ~/.nvm
```
- Remove the NVM path configuration lines from the **~/.profile** file. Open the file in a text editor:
```
vim ~/.profile
```
- Delete the following lines at the end of the file:
```
# NVM path management from ansible BEGIN
. ~/.nvm/nvm.sh
# NVM path management from ansible END
```

- Reboot the server
```
sudo reboot 
```

