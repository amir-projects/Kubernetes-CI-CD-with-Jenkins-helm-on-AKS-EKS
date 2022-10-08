# Add stable to helm

```sh
helm repo add stable https://charts.helm.sh/stable
helm repo search <chartname>

helm install repo stable/<chartname> <releasename>
  
helm pull <chartname>
  
helm package <chartname>

helm uninstall RELEASE_NAME
```
##example pull of mysql
```sh
helm pull stable/mysql
ls -ltra
tar -xvzf mysql-1.6.9.tgz
ls -ltra
cd mysql/
cd templates/
mv NOTES.txt NOTES.txt-old
cd ..
ls -ltr
vi chart.yaml
update version 1.6.9 -> 1.7.0
```
### always rembermber one step back

```sh
cd ..
ls -ltr
helm package mysql
Successfully packaged chart and saved it to: /var/lib/jenkins/mysql-1.7.0.tgz
```

