# jenkins_tests
# Jenkins installation.

following : https://www.jenkins.io/doc/book/installing/linux/

1. Install Ubuntu 24.04 on 192.168.2.246
2. Connect via ssh administrador .Martian?2001
    sudo apt update
    sudo apt install fontconfig openjdk-21-jre
    java -version   
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
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

# Crear git en willyrj repo 
echo "# jenkins_tests" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:willyrj/jenkins_tests.git
git push -u origin main


