### Make a connection for ssh from "Real machine" to Virtual machine:

#### 1. Install required package, in Virtual machine:
```bash
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install openssh-server
```
Once installed, the SSH service should be started automatically. 
If necessary, you can start (or stop, restart) the service manually via command:
```bash
$ sudo service ssh <start|stop|restart>
```
Verify that ssh service running
```bash
$ sudo systemctl status ssh
```
#### 2. Configure firewall and open port 22
```bash
$ sudo ufw allow ssh
$ sudo ufw enable
$ sudo ufw status
```
#### 3. SSH to a VM VirtualBox 
Select Enable Network Adapter (NAT)
click advanced -> select Port Forwarding button.

Options
* rule name = "ssh"
* Protocol = "TCP"
* Host port = 2222
* Host IP = 127.0.0.1 <IP for ssh>
* Guest port = 22
* Guest IP = 10.0.2.x <check by ifconfig command>
  
_PS: VirtualBox will create a private network (10.0.2.x) which 
will be connected to your host network using NAT._

You can make a connection by typing below command: (using git bash, putty or any tool you want for making a connection)
```bash
$ ssh -p 2222 [user]@127.0.0.1
```
🏖️
_refs:_ https://dev.to/yassineselllami/how-to-ssh-into-ubuntu-vm-virtualbox-from-host-machine-1kii

