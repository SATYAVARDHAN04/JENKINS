# JENKINS

## INSTALLATION
```bash
sudo curl -o /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

```bash
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
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

