# Hyperspace Node Docker Setup
I follow this guide: https://0xtnpxsgt.gitbook.io/airxnode/hyperspace-a.i/hyperspace-vps
Thank you 0xtnpxsgt!
## Step:1 Install Docker, if it is there you can skip it.
```Bash
docker --version
```
### If you have Installed to step 2!
```Bash
apt install docker.io -y
```
## Step:2 Pull Docker Image
```Bash
docker pull ubuntu:22.04
```
## Step:3 Run Docker Container
```Bash
docker run -it --name aios ubuntu:22.04
```
### * Ctrl + D to exit!
### Start Docker
```Bash
docker container start aios
```
## Step:4 Enter the Container
```Bash
docker container exec -it aios /bin/bash
```
## Step:5 Update Docker Ubuntu dan Install HyperSpace
```Bash
cd && apt update && apt upgrade && apt install curl screen -y
curl https://download.hyper.space/api/install | bash
source /root/.bashrc
```
## Step:6 Create Screen
```Bash
screen -S aios
```
## Step:7 Start aios
```Bash
aios-cli start
```
## After running, CTRL + A then D
## Step:8 Login
```Bash
aios-cli hive login
```
## Step:9 Select Tier
```Bash
aios-cli hive select-tier 5
```
## Step:10 Add Models
```Bash
aios-cli models add hf:TheBloke/phi-2-GGUF:phi-2.Q4_K_M.gguf
```
## Step:11 Backup Pubkey + Privkey
```Bash
aios-cli hive whoami
```
## Step:12 Connect aios
```Bash
aios-cli hive connect
```
## Step:13 Check Points
```Bash
aios-cli hive points
```
CTRL + D to exit docker

## Shortcut for Start, Login and Connect to Hive commands, if you've stopped you node
aios-cli start --connect
### Update node
aios-cli version
### Stop node
aios-cli kill
