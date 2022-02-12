### Install Jenkins on Ubuntu in general (18.04) 
I. Prerequisites
* OpenJDK JDK / JRE 8 - 64 bits or OpenJDK JDK / JRE 11 - 64 bits

II. Installing Instructions: 
* Install OpenJDK
```bash
sudo apt-get update
sudo apt-get install openjdk-8-jdk
```
* Install Jenkins Using Debian Repository
- Import trusted PGP Key for Jenkins
```bash
wget  https://pkg.jenkins.io/debian-stable/jenkins.io.key -P ~/
sudo apt-key add jenkins.io.key
# OK
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```
Note: If you use the combine command `wget -qO - https://pkg.jenkins.io/debian-stable/jenkins.io.key | apt-key add -`, 
you maybe get the below error when execute command `apt-get update` 
```
root@osboxes:~# apt-get update
Ign:1 https://pkg.jenkins.io/debian-stable binary/ InRelease
Get:2 https://pkg.jenkins.io/debian-stable binary/ Release [2,044 B]
Get:3 https://pkg.jenkins.io/debian-stable binary/ Release.gpg [833 B]
Ign:3 https://pkg.jenkins.io/debian-stable binary/ Release.gpg
Hit:4 http://us.archive.ubuntu.com/ubuntu bionic InRelease
Hit:5 http://security.ubuntu.com/ubuntu bionic-security InRelease
Hit:6 http://us.archive.ubuntu.com/ubuntu bionic-updates InRelease
Hit:7 https://esm.ubuntu.com/infra/ubuntu bionic-infra-security InRelease
Hit:8 https://esm.ubuntu.com/infra/ubuntu bionic-infra-updates InRelease
Hit:9 http://us.archive.ubuntu.com/ubuntu bionic-backports InRelease
Reading package lists... Done
W: GPG error: https://pkg.jenkins.io/debian-stable binary/ Release: The following signatures couldn't be verified because the public key is not available: NO_PU         BKEY FCEF32E745F2C3D5
E: The repository 'http://pkg.jenkins.io/debian-stable binary/ Release' is not signed.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
```
* Install Jenkins
```
sudo apt-get update
sudo apt-get install jenkins
```
Check status of Jenkins:
```
sudo systemctl status jenkins
```
If it isn’t enabled,/started automatically.
```
sudo systemctl enable jenkins
sudo systemctl start jenkins
```
* Configure Firewall
Allow port 8080 through the Ubuntu firewall.
```
sudo ufw allow 8080/tcp
```
* Initial Setup For Jenkins
Open-up your web browser and access it through the IP: PORT.
```
http://your_ip_or_domain:8080
```
The password get from:
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
- Choose Install suggested plugins or select specific plugins. 
- Set up the first admin user.
- Click on the Start using Jenkins button.
refs: https://phoenixnap.com/kb/install-jenkins-ubuntu














