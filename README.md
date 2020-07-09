ansible-controller主机:

1.more inventory.ini文件内容：  
[web1]  
ansible-node[1:1] ansible_connection=ssh ansible_user=root  
//执行命令  
cd /home/osboxes/ansible-code/inventory  
ansible web1 -m ping -i inventory.ini --private-key=/home/osboxes/.ssh/ansible                                           

2.playbook2.yaml文件内容：  
- hosts: web1  
  name: play-test  
  tasks:  
    - name: check host connection  
      ping:  
	    
playbook2.yaml执行命令：  
ansible-playbook playbook2.yaml -i ../inventory/inventory.ini  --private-key=/home/osboxes/.ssh/ansible  
ansible-playbook playbook3.yaml -i ../inventory/inventory.ini  --private-key=/home/osboxes/.ssh/ansible   
 

//创建密钥对  
ssh-keygen  
//拷贝key 到远程
ssh-copy-id -i .ssh/ansible.pub  root@192.168.3.27  
//执行远程shell命令
ansible all -m shell -a "more /usr/shunyi/A/test.c"  



Top 5 Programming Languages to Learn in 2020 to Get a Job Without a College Degree  
1.Python  
2.JavaScript  
3.SQL  
4.Swift  
5.Java  
  


