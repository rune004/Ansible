# Ansible

<h4> Ansible yaml tasks and VM's scripts </h4>


<h5> Use SSH without having to type in the password </h5>

ssh-add ~/.ssh/id_rsa

eval `ssh-agent -s`
ssh-add


<h5> Push SSH key to nodes </h5>

ssh-copy-id -i /home/rune/.ssh/id_rsa root@192.168.1.76

<h5> Tailscale Quick Installer </h5>

curl -fsSL https://tailscale.com/install.sh | sh

<h5> Allow root login </h5>

/etc/ssh/sshd_config

/etc/init.d/ssh restart


<h5> Proxmox LXC VPN Fix </h5>
This solution will fix any VPN you want to run such as Tailscale and OpenVPN

/etc/pve/lxc/

lxc.cgroup.devices.allow: c 10:200 rwm
lxc.mount.entry: /dev/net/tun dev/net/tun none bind,create=file