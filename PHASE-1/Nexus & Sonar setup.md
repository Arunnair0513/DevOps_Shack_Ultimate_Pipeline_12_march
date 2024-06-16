#  Setup

### 1. create nexus and sonar server on AWS instance

```bash 
run docker installation commands form docker offical site
Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

### 2. commands
```bash 
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 3. create container of sonar and nexus by pulling image from docker hub
```bash
docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
where 9000:hostport,9000:conatiner ports that has been opened
```
### 4. commands
```bash
docker run -d --name nexus -p 8081:8082 sonatype/nexus3
```
