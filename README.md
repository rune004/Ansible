# Ansible

<h4> Ansible yaml tasks and VM's scripts </h4>


<h5> Use SSH without having to type in the password </h5>

ssh-add ~/.ssh/id_rsa

eval `ssh-agent -s`
ssh-add


<h5> Push SSH key to nodes </h5>

ssh-copy-id -i /home/rune/.ssh/id_rsa root@192.168.1.76