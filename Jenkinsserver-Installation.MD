# Jenkins server Installation

### Prerequisites 
 1. EC2 Linux 7.x Instance upto

 2. OpenJDK
 https://www.jenkins.io/blog/2022/06/28/require-java-11/

## Install Java
We will be using openjdk for our demo, Get latest version from http://openjdk.java.net/install/
```sh
sudo amazon-linux-extras install java-openjdk11
```

### Confirm Java Version

_The output should be something like this,_
```
java -version
openjdk version "11.0.16" 2022-07-19 LTS
OpenJDK Runtime Environment (Red_Hat-11.0.16.0.8-1.amzn2.0.1) (build 11.0.16+8-LTS)
OpenJDK 64-Bit Server VM (Red_Hat-11.0.16.0.8-1.amzn2.0.1) (build 11.0.16+8-LTS, mixed mode, sharing)
```

## Install Jenkins
You can install jenkins using the rpm or by setting up the repo. We will setup the repo so that we can update it easily in future.
Get latest version of jenkins from https://pkg.jenkins.io/redhat-stable/
```sh
yum -y install wget
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo --no-check-certificate
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum -y install jenkins
```

### Start Jenkins
```sh
# Start jenkins service
systemctl start jenkins

# Setup Jenkins to start at boot,
systemctl enable jenkins

# Check Jenkins status,
systemctl status jenkins
```

#### Accessing Jenkins
By default jenkins runs at port `8080`, You can access jenkins at 8080 before than check the port listening 

```sh
netstat -ntlp
```

```sh
http://YOUR-SERVER-PUBLIC-IP:8080
```
#### Configure Jenkins
- The default Username is `admin`
- Grab the default password 
  - Password Location:`/var/lib/jenkins/secrets/initialAdminPassword`
- `Skip` Plugin Installation; _We can do it later_
- Change admin password
  - `Admin` > `Configure` > `Password`

### Test Jenkins Jobs
1. Create �new item�
1. Enter an item name � `My-First-Project`
   - Chose `Freestyle` project
1. Under Build section
	Execute shell : echo "Welcome to Jenkins Demo"
1. Save your job 
1. Build job
1. Check "console output"
