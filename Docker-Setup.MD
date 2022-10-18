## Install Docker
```sh
yum install docker
systemctl start docker
systemctl enable docker
systemctl status docker
```

## provide permissions to jenkins user in jenkins server to access docker

```sh
  [root@# cat /etc/group | grep -i docker
   docker:x:990:
```

```sh
  sudo usermod -aG docker jenkins
  sudo chmod 777 /var/run/docker.sock
```
## Add Jenkins user into sudoers file to get sudo access
```sh
   vi /etc/sudoers
   jenkins ALL=(ALL) NOPASSWD: ALL
```   
