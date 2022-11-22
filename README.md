<h1> Ansible yaml tasks and VM's scripts </h1>

<h3> Configure Ansible.cfg </h3>

<p>
inventory	= /etc/ansible/inventory/hosts
<br />
<br />
forks		= 5
<br />
sudo_user	= root
<br />
<br />
remote_user = root
<br />
<br />
become=True
<br />
become_method=sudo
<br />
become_user=root
<br />
become_ask_pass=False
</p>

<h3> Use SSH without having to type in the password </h3>

ssh-add ~/.ssh/id_rsa

eval `ssh-agent -s`
ssh-add


<h3> Push SSH key to nodes </h3>

ssh-copy-id -i /home/rune/.ssh/id_rsa root@192.168.1.76

<h3> Allow root login </h3>

/etc/ssh/sshd_config

/etc/init.d/ssh restart

<h3> Tailscale Quick Installer </h3>

curl -fsSL https://tailscale.com/install.sh | sh

<h4> Proxmox LXC VPN Fix </h4>
This solution will fix any VPN you want to run such as Tailscale and OpenVPN

/etc/pve/lxc/

lxc.cgroup.devices.allow: c 10:200 rwm
lxc.mount.entry: /dev/net/tun dev/net/tun none bind,create=file