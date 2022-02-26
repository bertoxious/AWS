# EC2 Commands

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