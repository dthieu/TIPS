### HOW TO INSTALL THE SECOND JENKINS (UBUNTU MACHINE)
#### 1. Download war file
```
wget <link war file> -P . 
```
* link war file: https://get.jenkins.io/war-stable/ <stable version>

#### 2. Installation
During installation, you must specify JENKINS_HOME and port: 
```
mkdir /var/lib/jenkins2
chmod 777 /var/lib/jenkins2
java -DJENKINS_HOME=/path/to/jenkins2 -jar jenkins.war --httpPort=8081
```
Follow the rest of the steps in the same order that Jenkins was installed such as install plugins, Create First Admin User,...

