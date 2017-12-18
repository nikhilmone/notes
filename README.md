vm.support@wipro.com

vmuser:Wipro@123
vmuser:123@wipro
sudo su -


Create users :

 oc create user nikhil --full-name=NikhilMone

 To see more information on roles and policies, use the 'get' and 'describe' commands on the following resources:
'clusterroles', 'clusterpolicy', 'clusterrolebindings', 'roles', 'policy', 'rolebindings', and 'scc'.

oc cluster up --public-hostname="10.210.16.157" --routing-suffix="10.210.16.157.nip.io"

identityProviders:
  - challenge: true
    login: true
    mappingMethod: claim
    name: my_htpasswd_provider
    provider:
      apiVersion: v1
      kind: HTPasswdPasswordIdentityProvider
      file: /opt/users.htpasswd

oc cluster up --host-data-dir=/opt/openshift_data --host-config-dir=/opt/openshift_conf --use-existing-config --public-hostname="10.210.16.157" --routing-suffix="10.210.16.157.nip.io"


error: Invalid MasterConfig /var/lib/origin/openshift.local.config/master/master-config.yaml
  assetConfig.publicURL: Invalid value: "https://127.0.0.1:8443/console/": must match oauthConfig.assetPublicURL
  oauthConfig.assetPublicURL: Invalid value: "https://10.210.16.157:8443/console/": must match assetConfig.publicURL


cp /var/lib/origin/openshift.local.config/master/master-config.yaml /root/


## Start Container Factory
oc cluster up --host-data-dir=/opt/openshift_data --use-existing-config=true --public-hostname="10.210.16.157" --routing-suffix="10.210.16.157.nip.io"





time="2017-09-11T11:26:35.567173838Z" level=error msg="response completed with error" err.code=unknown err.detail="denied: requested access to the resource is denied" err.message="unknown error" go.version=go1.7.6 http.request.host="172.30.1.1:5000" http.request.id=21dd6334-4f25-4b3b-b435-dc17062b8b73 http.request.method=HEAD http.request.remoteaddr="10.210.16.157:38182" http.request.uri="/v2/ubs/mypython/blobs/sha256:a0e32aa0faa650a2eb88ddf4bd6d2501520e6ec5203aeb2e78434a3b335ba987" http.request.useragent="docker/17.03.2-ce go/go1.7.5 git-commit/f5ec1e2 kernel/3.10.0-514.21.2.el7.x86_64 os/linux arch/amd64 UpstreamClient(go-dockerclient)" http.response.contenttype="application/json; charset=utf-8" http.response.duration=8.23559ms http.response.status=500 http.response.written=458 instance.id=5d64bfdd-ecdc-418d-9eab-eee9fafef42c openshift.auth.user="system:serviceaccount:ubs:builder" openshift.logger=registry vars.digest="sha256:a0e32aa0faa650a2eb88ddf4bd6d2501520e6ec5203aeb2e78434a3b335ba987" vars.name="ubs/mypython"

## Cluster users and policies
https://docs.openshift.com/enterprise/3.0/admin_guide/manage_authorization_policy.html

## Add users to the openshift
 htpasswd -c /var/lib/origin/openshift.local.config/master/users.htpasswd sacinporwal   ### Creates a new file everytime

 ## Add new user to existing file
 htpasswd /var/lib/origin/openshift.local.config/master/users.htpasswd nikhilmone



 ## GitLab Installation
 ```
 192  yum install -y curl openssh-server openssh-clients cronie
193  lokkit -s http -s ssh
194  yum install lokkit
195  lokkit -s http -s ssh
196  yum install postfix
197  service postfix start
198  chkconfig postfix on
199  curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
200  yum install -y gitlab-ce
201  gitlab-ctl reconfigure
202  cat  /etc/gitlab/gitlab.rb
203  vi /etc/gitlab/gitlab.rb
204  gitlab-ctl reconfigure
205  cat /var/spool/mail/root
206  lsof -i:8443
207  yum install lsof -y
208  lsof -i:8443
209  lsof -i:80
210  gitlab-ctl --help
211  gitlab-ctl status
212  gitlab-ctl start
213  lsof -i:80
214  lsof -i:8443
215  top
216  ps -ef | grep -i nginx
217  tail -100f /var/log/gitlab/nginx
218  netstat -anlp | grep -i git
219   gitlab-ctl status
220  vi /etc/gitlab/gitlab.rb
221  gitlab-ctl reconfigure
222  ps -ef | grep -i gitlab
223  gitlab-ctl status
224  vi /etc/gitlab/gitlab.rb
225  gitlab-ctl reconfigure
226  gitlab-ctl status
227  ps -ef | grep -i postgres
228  lsof -i:5432
229  lsof -i:9187
```

### To start containers without root

```
usermod -aG wheel nikhil
usermod -aG docker nikhil
```

## docker-compose


##### Upload docker images to openshift

```
719  oc get -is
720  docker images
721  docker rmi 172.30.1.1:5000/d2d/d2d_backend
722  docker rmi 172.30.1.1:5000/d2d_backend
723  docker rmi 172.30.1.1:5000/d2d/d2d_backend:1.0
724  docker rmi 172.30.1.1:5000/d2d_backend:1.0
725  docker rmi d2d:1.0
726  docker imsages
727  docker images
728  clear
729  history
730  docker login -p EkrE1n-Ed-EctE-eYEqHPVKHwm3IIPt2btopEyBhfGQ -e unused -u unused 172.30.1.1:5000
731  docker tag d2d:latest 172.30.1.1:5000/d2d/d2d_backend:1.0
732  docker push 172.30.1.1:5000/d2d/d2d_backend:1.0
733  oc get is --all
734  oc get is
735  oc project
736  oc get is
737  docker run -it d2d
```



##### Docker installation


```
My Server : 10.210.16.102

nikhil@123
123@wipro
sudo su -   yabadabad
```


######### Private Docker Registry ##########
```
docker pull 10.210.16.102:5000/my-ubuntu


[root@AWSGA-D-CTTEST1 ~]# cat /etc/docker/daemon.json
{
   "insecure-registries": [
     "172.30.0.0/16",
     "10.210.16.204:8083",
     "10.210.16.204:8082"
   ]
}


docker run -d -p 5000:5000 --restart=always --name registry -v /home/nikhil/data:/var/lib/registry registry:2
docker pull ubuntu:16.04
docker tag ubuntu:16.04 10.210.16.102:5000/my-ubuntu
docker push 10.210.16.102:5000/my-ubuntu
docker image remove ubuntu:16.04
docker image remove localhost:5000/my-ubuntu
docker image remove 10.210.16.102:5000/my-ubuntu
docker pull 10.210.16.102:5000/my-ubuntu

curl http://10.210.16.102:5000/v2/_catalog
{"repositories":["my-ubuntu"]}
```

#ssh tunneling :
```
ssh -f <user>@<remote-ip> -L <local-ip>:<local-port>:<remote-ip>:<remote-port> -N
```

# Registry UI
```
docker run -p 80:8080 -e REG1=http://10.210.16.102:5000 atcol/docker-registry-ui

docker run -it -p 8080:8080 --restart=always --name registry-web --link registry -e REGISTRY_URL=http://10.210.16.157:8000/v2 -e REGISTRY_NAME=http://10.210.16.157:5000/v2 hyper/docker-registry-web
```
# Nexus Repository Manager

https://github.com/TerrenceMiao/nexus/wiki/Setup-Docker-Private-Registry-in-Nexus-Repository-OSS-3.0.0
```
docker run -d -p 8081:8081 -p 8082:8082 -p 8083:8083 --restart=always --name nexus -v /home/nikhil/nexus-data:/nexus-data sonatype/nexus3
```


#On client side :

```
137  docker login -u admin -p admin123 10.210.16.204:8082
138  docker login -u admin -p admin123 10.210.16.204:8083

docker tag 10.210.16.204:8081/tomcat:8.5 10.210.16.204:8083/tomcat:8.5
docker push 10.210.16.204:8083/tomcat:8.5

146  docker pull 10.210.16.204:8082/tomcat
147  docker images
148  docker pull 10.210.16.204:8082/tomcat:8.5
149  docker images
150  docker rmi 10.210.16.204:8083/tomcat
151  docker images
152  docker rmi 10.210.16.204:8083/tomcat:8.5
153  docker images
154  docker pull 10.210.16.204:8083/tomcat:8.5

164  docker pull 10.210.16.204:8083/nginx
165  docker pull 10.210.16.204:8082/nginx


109  mkdir /home/nikhil/nexus-data && chown -R 200 /home/nikhil/nexus-data
110  ls -al
111  chmod -R 777 /home/nikhil/nexus-data
112  pwd
113  ls -al
114  cd nexus-data/
115  ls =al
116  ls -al
117  docker run -d -p 8081:8081 --restart=always --name nexus -v /home/nikhil/nexus-data:/nexus-data sonatype/nexus3
```


# Run custom images in openshift
```
oc login
oc project d2d
431  oc whoami -t
432  docker login -u nikhil -p 8-KysvDi5i4zGz3nw_pgUJPvjASXoDkvldYm1VpQ-mU 172.30.1.1:5000
433  docker push 172.30.1.1:5000/d2d/tomcat
```
# Running priviledged containers
```
oc login <user>
oc adm policy add-scc-to-user anyuid -z default

oc project <project-name>
oc adm policy add-scc-to-user anyuid system:serviceaccount:<project-name>:default
oc new-app --docker-image=10.210.16.204:8083/lrc:0.2 --insecure-registry=true
```

add nexus repo secret in the deployment config ... then deploy



# docker-ce installation

```
715  yum install -y yum-utils   device-mapper-persistent-data   lvm2
716  yum-config-manager     --add-repo     https://download.docker.com/linux/centos/docker-ce.repo
717  yum install docker-ce
718  yum install http://mirror.centos.org/centos/7/extras/x86_64/Packages/container-selinux-2.21-1.el7.noarch.rpm
719  yum install docker-ce
720  clear
721  docker ps
722  systemctl start docker
723  systemctl enable docker
724  docker ps
```


#  Save and load docker images     document_type_identifier:0.1

```
docker login -u anonymous -p anonymous
docker pull 10.210.16.204:8083/document_type_identifier:0.1
docker save -o document_type_identifier.tar 10.210.16.204:8083/document_type_identifier:0.1
scp document_type_identifier.tar vmuser@10.210.16.129:~/
ssh vmuser@10.210.16.129
docker load -i /home/vmuser/document_type_identifier.tar
```

# Open Firewall Ports
```
sudo iptables -I INPUT -p tcp --dport 8080 -j ACCEPT
```

# Login to server as desired users
Check `/etc/ssh/sshd_config` for allowed users list. If it is OK, the problem is more complex. Try to connect as "ssh codeuser@your-server -v"


# To check the ports opened
```
iptables -L -vn
netstat -tuplen

firewall-cmd --list-ports | grep -w <Port No.>
iptables --list-rule | grep -w <Port No.>
sudo nmap -sS 10.210.16.129
```
### Ansible password-less login for jenkins :

```
sudo su -s /bin/bash jenkins
ssh-keygen -t rsa
ssh-copy-id vmuser@10.210.16.129
```

##### port forwarding

# Forward the 4200 port of remote server to local 8080
```
ssh -L 4200:localhost:4200 vmuser@10.210.16.102
ssh -L 8000:localhost:8000 vmuser@10.210.16.102
ssh -L 3002:localhost:3002 vmuser@10.210.16.102
ssh -L 3001:localhost:3001 vmuser@10.210.16.102
ssh -L 3000:localhost:3000 vmuser@10.210.16.102
```

## Docker Disk space issues

#Remove dangling images
```
docker images -q --filter dangling=true | xargs docker rmi
docker images --no-trunc | grep '<none>' | awk '{ print $3 }'| xargs -r docker rmi
docker ps --filter status=dead --filter status=exited -aq | grep -iv openshift | xargs docker rm -v
```

# Kill all containers
```
docker kill $(docker ps -q)
```

#Script

```
#!/bin/bash

# remove exited containers:
docker ps --filter status=dead --filter status=exited -aq | xargs -r docker rm -v

# remove unused images:
docker images --no-trunc | grep '<none>' | awk '{ print $3 }' | xargs -r docker rmi

# remove unused volumes:
find '/var/lib/docker/volumes/' -mindepth 1 -maxdepth 1 -type d | grep -vFf <(
  docker ps -aq | xargs docker inspect | jq -r '.[] | .Mounts | .[] | .Name | select(.)'
) | xargs -r rm -fr
```


# Compose up individual service

```
docker-compose stop pdf2html_erm

docker-compose up -d --no-deps pdf2html_erm
```
