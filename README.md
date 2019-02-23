Create user :

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
oc cluster up --host-data-dir=/opt/openshift_data --use-existing-config=true --public-hostname="10.210.16.157" --routing-suffix="10.210.16.157"



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
yum install -y yum-utils device-mapper-persistent-data lvm2 -y
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum install http://mirror.centos.org/centos/7/extras/x86_64/Packages/container-selinux-2.21-1.el7.noarch.rpm -y
yum install docker-ce -y

docker ps
systemctl start docker
systemctl enable docker
docker ps
```
# docker-compose installaion

```
curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
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

# Clean everything:

docker system prune -a

#Remove dangling images
```
docker images -q --filter dangling=true | xargs docker rmi
docker images --no-trunc | grep '<none>' | awk '{ print $3 }'| xargs -r docker rmi
docker ps --filter status=dead --filter status=exited -aq | grep -iv openshift | xargs docker rm -v
```

# Kill all containers
```
docker kill $(docker ps -q)
docker stop $(docker ps -aq)
```

#Script

```
#!/bin/bash

# remove exited containers:
docker ps --filter status=dead --filter status=exited -aq | xargs -r docker rm -v

# remove unused images:
docker images --no-trunc | grep '<none>' | awk '{ print $3 }' | xargs -r docker rmi -f

# remove unused volumes:
find '/var/lib/docker/volumes/' -mindepth 1 -maxdepth 1 -type d | grep -vFf <(
  docker ps -aq | xargs docker inspect | jq -r '.[] | .Mounts | .[] | .Name | select(.)'
) | xargs -r rm -fr
```


# yum install epel-release

# Bring up individual service

```
docker-compose stop pdf2html_erm

docker-compose up -d --no-deps pdf2html_erm
```

# LDAP details

hyd-mkd-dc03.wipro.com:389
10.156.50.100

pne-hjn-dc05.wipro.com:389
10.113.50.100

# CMR for port opening
CMR# 32428

### Gitlab backup
vi /etc/gitlab/gitlab.rb

---
gitlab_rails['manage_backup_path'] = true
gitlab_rails['backup_path'] = "/AWSGB-D-CTTEST2_data/gitlab_backup"

###! Docs: https://docs.gitlab.com/ce/raketasks/backup_restore.html#backup-archive-permissions
gitlab_rails['backup_archive_permissions'] = 0644

# gitlab_rails['backup_pg_schema'] = 'public'

###! The duration in seconds to keep backups before they are allowed to be deleted
gitlab_rails['backup_keep_time'] = 604800
---

gitlab-rake gitlab:backup:create
sudo sh -c 'umask 0077; tar -cf $(date "+etc-gitlab-%s.tar") -C / etc/gitlab'

## Nodejs Installation

http://yoember.com/nodejs/the-best-way-to-install-node-js/


http://nodejs.org/dist/

curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash

nvm list
nvm ls-remote
nvm install 8.9.4
nvm use 8.9.4
nvm alias default 8.9.4
node -v
npm install -g npm
npm -v

##############################

8081,8083,8086,8087,8089,8091,8093

liability, duratio, elastic, dno, bold  

 mvn deploy:deploy-file -DgroupId=com.oracle -DartifactId=ojdbc6 -Dversion=11.2.0.3 -Dpackaging=jar -Dfile=ojdbc6.jar -DgeneratePom=true -DrepositoryId=nexus-group -Durl=http://10.210.16.204:8081/repository/nexus-group/

 sudo iptables -I INPUT -p tcp --dport 8893 -j ACCEPT


 # Install Apache

 Install Apache:
First, clean-up yum:
sudo yum clean all
As a matter of best practice we’ll update our packages:
sudo yum -y update
Installing Apache is as simple as running just one command:
sudo yum -y install httpd
Allow Apache Through the Firewall
Allow the default HTTP and HTTPS port, ports 80 and 443, through firewalld:
sudo firewall-cmd --permanent --add-port=80/tcp
sudo firewall-cmd --permanent --add-port=443/tcp
And reload the firewall:
sudo firewall-cmd --reload

Configure Apache to Start on Boot
And then start Apache:
sudo systemctl start httpd
Be sure that Apache starts at boot:
sudo systemctl enable httpd
Other useful commands for Apache
To check the status of Apache:
sudo systemctl status httpd
To stop Apache:
sudo systemctl stop httpd

# Install Pip on Ubuntu Jessie 8:

Installing Pip
Python pip package is available on Debian apt-get package repository. But before we can install pip, we have to install necessary packages to run pip.

# sudo apt-get update
# sudo apt-get install python-dev build-essential
Now we can install Pip using the following command:

# sudo apt-get install python-pip
However the pip version included on Debian apt-get can be outdated, we can upgrade pip to the latest version by using the command below.

# pip install --upgrade pip


# To replace a string from all the files in a folder

cd /path/to/your/folder
sed -i 's/foo/bar/g' *

# pass environment variable to python file
os.environ['rabbitmq_server']

## environment variable globally:
```
[root@AWSGA-D-CTNFS1 ~]# cat /etc/environment
GOOGLE_APPLICATION_CREDENTIALS=/home/nikhil/negative-news/micro-services/news-search-service/key.json
```
```
[root@AWSGA-D-CTNFS1 ~]# cat ~/.bashrc
# .bashrc
export GOOGLE_APPLICATION_CREDENTIALS=/home/nikhil/negative-news/micro-services/news-search-service/key.json
# User specific aliases and functions

alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'

# Source global definitions
if [ -f /etc/bashrc ]; then
        . /etc/bashrc
fi
```

# Install Rabbitmq:

yum install epel-release
yum install rabbitmq-server

# install mongodb

https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/

809  vi /etc/yum.repos.d/mongodb-org-3.6.repo

```
[mongodb-org-3.6]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.6/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.6.asc
```

```
[mongodb-org-3.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.4.asc
```

yum install -y mongodb-org
systemctl status mongod
systemctl start mongod
systemctl enable mongod
systemctl status mongod

# Running cAdvisor

docker run \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:rw \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --volume=/dev/disk/:/dev/disk:ro \
  --publish=8080:8080 \
  --detach=true \
  --name=cadvisor \
  google/cadvisor:latest


  docker run   --volume=/:/rootfs:ro   --volume=/var/run:/var/run:rw   --volume=/sys:/sys:ro   --volume=/var/lib/docker/:/var/lib/docker:ro   --volume=/dev/disk/:/dev/disk:ro   --publish=8099:8080   --detach=true   google/cadvisor:latest

# S3 bucket
Account ID – wipro-aws
IAM user – viveks3
Password –Wipro@123

# NodeJS PM2

CMD ["pm2", "start", "processes.json", "--no-daemon"]

Use a process file to manage these two applications: http://pm2.keymetrics.io/docs/usage/application-declaration/

For example - process.yml:

apps:
  - script : 'npm'
    args   : 'run dev'
    cwd    : './backend'
    name   : 'backend'
  - script : 'npm'
    args   : 'run dev'
    cwd    : './frontend'
    name   : 'frontend'
Then in the Dockerfile:

CMD ['pm2-docker', 'process.yml']
Documentation about PM2/Docker integration: http://pm2.keymetrics.io/docs/usage/docker-pm2-nodejs/


## For Python

http://pm2.keymetrics.io/docs/usage/quick-start/

# supervisord

http://supervisord.org/
