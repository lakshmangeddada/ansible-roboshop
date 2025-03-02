# ansible-roboshop
step1: Install python3 and ansible.

step2: add hosts IP or hostname in inventory file. (ansible must be installed in the hosts.)

  We can keep either IP address or Hostname.
  • Grouping can be done either individual files based on environment or based on component and even together and that always depends upon the architecture design that project had.
  
  • In environments like a cloud where the nodes are too dynamic and where your IP addresses always change frequently, we need to work on some dynamic inventory management.

  How to add in linux:
  #create a temporary invoice folder
  vim /tmp/inv
  
  #add IP address of the VM in this file and save.
  ex: 10.242.12.151

  Now connect the VM from ansible server.
  ** ansible -i /tmp/inv all -e ansible_user=centos -e ansible_password=DevOps321 -m ansible.builtin.ping 
  
  ** ansible -i 10.242.12.151, all -e ansible_user=centos -e ansible_password=DevOps321 -m ansible.builtin.ping (for single server)
  
    all: All the hosts added in inventory file.
    ansible_user: user name of the VM to login
    ansible_password: password to login to the VM
    ansible.builtin.ping: ping collection in ansible.
    
  ansible uses SSH behind the scene.

  If you want to connect to particular group then add group name in the inventory file.
  
** ansible -i /tmp/inv App -e ansible_user=centos -e ansible_password=DevOps321 -m ansible.builtin.ping 
    App: group name
  
