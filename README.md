# MeshCentral-Nginx-ProxyManager Ubuntu 22.04 LTS
##Install Docker
```sh
sudo apt update -y && apt upgrade -y
```
```sh
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
```sh
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```sh
sudo apt update
```
```sh
sudo apt-cache policy docker-ce
```
```sh
sudo apt install docker-ce -y
```
```sh
sudo systemctl status docker
```
```sh
sudo systemctl enable docker
```
```sh
sudo usermod -aG docker username (Remember to replace username with your user)
```
## Install Docker Compose
```sh
sudo curl -L https://github.com/docker/compose/releases/download/v2.27.1/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```
```sh
sudo chmod +x /usr/local/bin/docker-compose
```
```sh
docker-compose --version
```
Create directory at /opt/nginx
```sh
mkdir -p /opt/nginx
```
```sh
cd /opt/nginx
```
```sh
vi docker-compose.yml
```
content in the file docker-compose.yml
```sh
docker-compose up -d
```
After all the Containers are up
Access NginxManager with port 8181
http://IP:8181

Default Administrator User

Email:    admin@example.com
Password: changeme

Then create proxy hosts pointing to port 8086