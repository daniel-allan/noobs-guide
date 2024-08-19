## Change ip of porxmox
    - ```change the ip address in the /etc/network/interfaces ```
    - confirm the changes using ```ip a```
    - Or ping the gateway ```192.168.1.1```

## Create SSH keys
    - create ssh keys using the command ssh-keygen
    eg: ```ssh-keygen -t ed25519 -f ~/.ssh/[filename] -C "[COMMENT]"```
    ssh-keygen is the program
    -t is to specify the type of algorithm 
    -f to specify the file where the key is saved 
    -C to have a useful comment
    
### copy the shh key to the server
    - copy the ssh key to the server using ssh-copy-id command
    eg ```ssh-copy-id -i [path to public key] user_of_server@ip_of_server```
        -i is to specify the identify file aka pub key
### disable root login, password based auth
    - edit the /etc/ssh/sshd_config file
    ``` change the premitrootlogin to no
        change the passwordAuthentication to no
        chnage the publicAuthentication to yes ```
### Create a shh config file
    - create a config file in .ssh/config
    eg: ```Host debian-machine
           HostName [ip]
           IdentityFile [path to ssh private key]
           User [user of server]
    ```
    - To login to shh using the config use the following command ``` ssh debian-machine ```

## Turn Of acpi logs in debian
    - open /etc/default/grub
    - add apci=off to ```GRUB_CMDLINE_LINUX_DEFAULT=```
    - sudo update-grub
    - reboot
## create ansible vault and use it in playbook
    ansible-vault encrypt [path to secret file.yml]
        - To use it with the playbook ```ansible-playbook --ask-become-pass -e @vault/secrets.yml --ask-vault-pass  deploy-all.yml ```

## playbook learnings
    - when replacing the text with the lineinfile if the text to be replaced is at the start of the file then no problem if not need to specify the indentation too
    - To create a file do not use shell module insted use the file module to create a file if multiple files to be created use loops 
