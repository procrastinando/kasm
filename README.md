## Increase the swap memory:
Add 1G per workspace:
```
fallocate -l 1G /swapfile
chmod 600 /swapfile
mkswap /swapfile
swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```
## Install Kasm
```
mkdir tmp && cd /tmp
curl -O https://kasm-static-content.s3.amazonaws.com/kasm_release_1.12.0.d4fd8a.tar.gz
tar -xf kasm_release_1.12.0.d4fd8a.tar.gz
```
Standard installation (requires 50G of free space):
```
sudo bash kasm_release/install.sh
```
To skip the Images installation and changing the port:
```
sudo bash kasm_release/install.sh -I -L 8443
```
## Add new workspaces
```
Workspace Type: Container
Friendly Name: Brave
Description: Brave Browser
Thumbnail URL: https://upload.wikimedia.org/wikipedia/commons/thumb/9/9d/Brave_lion_icon.svg/654px-Brave_lion_icon.svg.png
Docker Image: kasmweb/brave:1.11.0-rolling
Friendly Name: Brave Browser
Cores: 1
Memory (MB): 1024
GPU Count: 0
Docker Registry: hub.docker.com
Persistent Profile Path: /home/{username}/brave
```
