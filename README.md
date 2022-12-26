# howto install docker on ubuntu server 22.04 LTS
config ip address:
```code
network:
  ethernets:
    enp2s0f0:
      dhcp4: false
      addresses:
      - 192.168.13.2/24
      routes:
      - to: default
        via: 192.168.13.1
      nameservers:
        addresses:
        - 1.1.1.1
        - 8.8.8.8
        - 9.9.9.9
        search: []
  version: 2
```
#
step 1
```code
sudo apt update
```
#
step 2
```code
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```
#
step 3
```code
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
#
step 4
```code
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
#
step 5
```code
sudo apt update
```
#
step 6
```code
sudo apt install docker-ce -y
```
#
step 7: cek status docker
```code
sudo systemctl status docker
```
#
step 8
```code
sudo usermod -aG docker ${USER}
```
#
step 9
```code
su - ${USER}
```
#
step 10
```code
groups
```
## Next: Install Docker Compose
step 11
```code
mkdir -p ~/.docker/cli-plugins/
```
step 12
```code
curl -SL https://github.com/docker/compose/releases/download/v2.3.3/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose
```
#
step 13
```code
chmod +x ~/.docker/cli-plugins/docker-compose
```
