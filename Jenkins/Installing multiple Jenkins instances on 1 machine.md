### HOW TO INSTALL THE SECOND JENKINS (UBUNTU MACHINE)
#### 1. Download war file
```
wget <link war file> -P . 
```
* Link war file: https://get.jenkins.io/war-stable/ <stable version>

#### 2. Installation
During installation, you must specify JENKINS_HOME and port: 
```sh
mkdir /var/lib/jenkins2
chmod 777 /var/lib/jenkins2
java -DJENKINS_HOME=/path/to/jenkins2 -jar jenkins.war --httpPort=8081
```
Follow the rest of the steps in the same order that Jenkins was installed such as install plugins, Create First Admin User,...

#### 3. Start Jenkins
* To start the Jenkins up, we use the same method with installing:
```sh
java -DJENKINS_HOME=/path/to/jenkins2 -jar jenkins.war --httpPort=8081  
```
* To set it to run automatically when the computer boots up, we can add an @reboot [cron](http://en.wikipedia.org/wiki/Cron) task:
* Running ```crontab -e``` will allow you to edit your cron.
* Adding a line like below to it:
```sh
@reboot java -DJENKINS_HOME=/path/to/jenkins2 -jar jenkins.war --httpPort=8081
```
will execute that script once your computer boots up.

<u>refs:</u> https://askubuntu.com/questions/814/how-to-run-scripts-on-start-up


