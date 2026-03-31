# JENKINS

## INSTALLATION
```bash
sudo curl -L \
https://pkg.jenkins.io/redhat-stable/jenkins.repo \
-o /etc/yum.repos.d/jenkins.repo
```

```bash
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

```bash
sudo dnf repolist | grep jenkins
```

```bash
sudo yum install fontconfig java-21-openjdk jenkins -y
```

```bash
sudo systemctl daemon-reload
```

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
## SETUP

```bash
sudo yum install -y cloud-utils-growpart
```

```bash
sudo growpart /dev/xvda 4
```

```bash
lsblk
```

```bash
sudo pvresize /dev/xvda4
```

```bash
# Increase root
sudo lvextend -L +10G /dev/RootVG/rootVol
sudo xfs_growfs /

# Increase /var (VERY IMPORTANT)
sudo lvextend -L +10G /dev/RootVG/varVol
sudo xfs_growfs /var

# Increase /var/log
sudo lvextend -L +5G /dev/RootVG/logVol
sudo xfs_growfs /var/log

# Use remaining space for /home
sudo lvextend -l +100%FREE /dev/RootVG/homeVol
sudo xfs_growfs /home
```

```bash
df -h
```