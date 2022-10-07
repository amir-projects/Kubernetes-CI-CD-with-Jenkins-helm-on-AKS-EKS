### Jenkins server setup with Helm to deploy into Kubernetes cluster

## Switch to jenkins user

```sh
# su - jenkins
-bash-4.2$ id
uid=994(jenkins) gid=992(jenkins) groups=992(jenkins),990(docker)


## Download and Install helm 
```sh
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

## Test with helm command
```sh
helm version
version.BuildInfo{Version:"v3.10.0", GitCommit:"ce66412a723e4d89555dc67217607c6579ffcb21", GitTreeState:"clean", GoVersion:"go1.18.6"}
helm list
```

## Copy config file from EKS Management host to Jenkins home directory

## login EKS mgmt host
```sh
ls -ltra 
cd .kube
cat config 
```
## login jenkins server
```sh
-bash-4.2$ pwd
/var/lib/jenkins
mkdir .kube
cd .kube
vi config
copy file from k8s config file 
```
