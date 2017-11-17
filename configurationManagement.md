1. Create a folder boxes
2. Create two folders /boxes/ansible and boxes/node0
3. Inside both folders, do vagrant init ubuntu/trusty64 and modify the vagrant file - Use hostOnly network configuration and change the IP of each other.
4. vagrant up 
5. Go into ansible folder and do vagrant ssh -> This will open up the ansible server.
6. touch inventory
7. mkdir keys
8. Go into keys and do touch node0.key
9. Now go to boxes/node0 folder and go into .vagrant/machines/../ and open the private_key using notepad++ and copy the contents
10. Go to  ansible server and nano node0.key and paste the contents.
11. Now need to tell ansible what all nodes  to be configured using ansible. For this, nano inventory file previously created and paste the command: 
```
[nodes]
192.168.33.100 ansible_ssh_user=vagrant ansible_ssh_private_key_file=./keys/node0.key
```
Basically, this is telling ansible that the first is the IP of the node and its ssh_private key is keys/node0.key
We can add many such lines, for configuring multiple nodes. How easy!

12. Now, run the ansible commands as shown in the readme.md

