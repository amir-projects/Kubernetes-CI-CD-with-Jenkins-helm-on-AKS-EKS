# Install and Configure Maven & git in Jenkins server

## Install Maven
```sh
yum install wget
wget https://mirror.lyrahosting.com/apache/maven/maven-3/3.8.1/binaries/apache-maven-3.8.1-bin.tar.gz](https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz
tar -xvzf apache-maven-3.8.6-bin.tar.gz
export M2_HOME=/opt/apache-maven-3.8.6
export M2=$M2_HOME/bin
PATH=$PATH:$M2
# To set it permanently update your .bash_profile
source ~/.bash_profile

Validate Maven

mvn version
```

## Install git
```sh
yum install git


```

##Assign shell to jenkins user
##By default jenkins user don't have the shell

```sh
cat /etc/passwd
jenkins:x:994:992:Jenkins Automation Server:/var/lib/jenkins:/bin/false
```

##Assign shell to jenkins user
```sh
vi /etc/passwd
change shell from /bin/false to /bin/bash
jenkins:x:994:992:Jenkins Automation Server:/var/lib/jenkins:/bin/bash
```
