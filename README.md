# howto install docker on ubuntu server 22.04 LTS
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
