# Ansible

<h3> Ansible yaml tasks and VM's scripts </h3>


<h4> Use SSH without having to type in the password </h4>

ssh-add ~/.ssh/id_rsa

eval `ssh-agent -s`
ssh-add


<h4> Push SSH key to nodes </h4>

ssh-copy-id -i /home/rune/.ssh/id_rsa root@192.168.1.76

<h4> Allow root login </h4>

/etc/ssh/sshd_config

/etc/init.d/ssh restart

<h4> Tailscale Quick Installer </h4>

curl -fsSL https://tailscale.com/install.sh | sh

<h5> Proxmox LXC VPN Fix </h5>
This solution will fix any VPN you want to run such as Tailscale and OpenVPN

/etc/pve/lxc/

lxc.cgroup.devices.allow: c 10:200 rwm
lxc.mount.entry: /dev/net/tun dev/net/tun none bind,create=file