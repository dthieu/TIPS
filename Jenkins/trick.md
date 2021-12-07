### 1. Run a script on a node
```
node('LAPTOP-3QRSAL6A') {
    stage('Init') {
        echo "Init"
    }
    stage('Deploy') {
        echo "Deploy"
        bat 'cmd.exe /c c:\\jenkins\\ex.bat'
    }
}
```
### 2. Mail to ...
```
mail bcc:'ccc@aaa.com.cn' , body:'haha , this hr .', cc:'bbb@aaa.com.cn',subject:'welcome to aaa bbb cc join the abc.inc ',from ".replyTo:",to:'aaa@aaa.com.cn'
```
Example:
```  
post {
    success {
      mail to: "XXXXX@gmail.com", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
    }
    failure {
      mail to: "XXXXX@gmail.com", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
    }
}
```
### 3. Load file from e:\jenkins\hello.xxx
```
load 'e:\\jenkins\\hello.xxx'
```
### 4. Checks if running on a Unix-like node
Example
```
if (isUnix())
{
  echo "Bash/shell script"
}
```
### 5. Change current directory
Example : change the dir to the e:
```
dir("e:\\")
{
   echo "I am at e"
}
```
### 6. Build a job
Example: to build a job : ```TEST_SCRIPT``` with parameters : ```TEST_STAGES```
```
build job: 'TEST_SCRIPT', parameters: [[$class: 'StringParameterValue', name: 'TEST_STAGES', value: 'sss']], propagate: false
```
