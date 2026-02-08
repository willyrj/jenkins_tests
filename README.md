# jenkins_tests

## Jenkins installation.

following : https://www.jenkins.io/doc/book/installing/linux/

1. Install Ubuntu 24.04 on 192.168.2.246
2. Connect via ssh administrador .Martian?2001
    sudo apt update
    sudo apt install fontconfig openjdk-21-jre
    java -version   
    sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
    echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt update
    sudo apt install jenkins

    journalctl -u jenkins (look for password)
    or /var/lib/jenkins/secrets/initialAdminPassword
    4008abebbc774d0b80934c376b2ef3bc

    sudo ufw status
    sudo ss -tulnp

It was on port 8080 enter password
Install sugested plugins

administrador .Martian_2001 willy@rjurado.com
Jenkins URL: http://192.168.2.246:8080

## Crear git en willyrj repo 
echo "# jenkins_tests" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:willyrj/jenkins_tests.git
git push -u origin main

## Download repo del curso
https://github.com/sandervanvugt/gitops/tree/main

## Instalar software on Jenkins Server
### Instalar Docker
# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

* Correct error for current user
permission denied while trying to connect to the docker API at unix:///var/run/docker.sock
sudo usermod -aG docker $USER

### Install Kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
copio desde nodo 1 /root/.kube/config al /home/administrador/.kube/config
puedo acceder al cluster.