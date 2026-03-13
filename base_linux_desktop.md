## Linux Desktop Base

[Back to index](README.md)

---
### 1. Base OS Preparation

**Update System**

```bash
sudo apt update 
sudo apt upgrade -y
```

**Install Base Utilities**

```bash
sudo apt install -y \
  curl wget git git-lfs htop unzip \
  net-tools jq ca-certificates \
  gnupg lsb-release software-properties-common
```
---
### 2. Install SSH Server

**Install SSH Server**

```bash
sudo apt update
sudo apt install -y openssh-server
```

**Verify**
```bash
sudo systemctl status ssh
```
**If it is not runing**
```bash
sudo systemctl start ssh
```
**Enable SSH at startup**
```bash
sudo systemctl enable ssh
```
---
### 3. Docker Installation 

**Remove old versions (if any)**

```bash
sudo apt remove -y docker docker-engine docker.io containerd runc
```

**Add Docker Repo's PGP Key**

```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
**Add Docker Repo**

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
**Install Docker + Compose**

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
**Enable Docker**

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

**Add user (so you don't have to sudo it every time you type docker)**

```bash
sudo usermod -aG docker $USER
```

**[IMPORTANT] You must relogin/reboot before verifying**

```bash
docker version
docker compose version
```

**Create Docker Baseline Configuration**

```bash
sudo mkdir -p /etc/docker
```

```bash
sudo tee /etc/docker/daemon.json >/dev/null <<'EOF'
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "50m",
    "max-file": "5"
  },
  "features": {
    "buildkit": true
  }
}
EOF
```
```bash
sudo systemctl restart docker
```
---
