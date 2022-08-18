# EC2 Commands

## copy and login commands
```
ssh -i Example.pem ec2-user@public-ipv4-address
scp -i Example.pem -r file/folder-path ec2-user@public-ipv4-address:~
```

## Setting up docker 

```
sudo yum update
sudo yum search docker
sudo yum info docker 
sudo yum install docker 
```

## Setting up docker compose 

```
wget https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)
sudo mv docker-compose-$(uname -s)-$(uname -m) /usr/local/bin/docker-compose
sudo chmod -v +x /usr/local/bin/docker-compose
```

## enable docker service

```
sudo systemctl enable docker.service 
sudo systemctl start docker.service
``` 

## finding status

```
sudo systemctl status docker.service 
```

## getting version

```
docker version
docker-compose version 
```

## controlling docker service 

```
sudo systemctl start docker.service 
sudo systemctl stop docker.service 
sudo systemctl restart docker.service 
sudo systemctl status docker.service 
```

## add docker to group

```
sudo groupadd docker 
sudo usermod -aG docker $USER
```

## if got permission denied while docker compose up

```
sudo chmod 666 /var/run/docker.sock  
```

## openjdk 17 installation
```
wget https://download.java.net/java/GA/jdk17/0d483333a00540d886896bac774ff48b/35/GPL/openjdk-17_linux-x64_bin.tar.gz  
tar xvf openjdk-17_linux-x64_bin.tar.gz  
sudo mv jdk-17 /opt/  
sudo tee /etc/profile.d/jdk.sh <<EOF  
export JAVA_HOME=/opt/jdk-17  
export PATH=\$PATH:\$JAVA_HOME/bin  
EOF  
source /etc/profile.d/jdk.sh  
java --version   
```

## jenkins installation
```
sudo wget -O /etc/yum.repos.d/jenkins.repo \  
    https://pkg.jenkins.io/redhat-stable/jenkins.repo  
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key  
sudo yum install jenkins -y  
sudo systemctl enable jenkins  
sudo systemctl start jenkins  
```

## get jenkins initial password
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
