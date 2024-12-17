# Jenkins-setup

JENKINS 

- Create a Server on AWS OR AZURE VM
- Cd downloads
- Chmod 600 tony-key.pem 
  -   shh -I Tony-key.pem ubuntu@1234566
- Sudo apt update && sudo apt upgrade -y

RUN THE BELOW COMMANDS TO INSTALL JAVA AND JENKINS
Install Java

Sudo apt update
Sudo apt install openjdk-17-jre

VERIFY JAVA IS INSTALLED

Java -version

Now, you can proceed with installing Jenkins

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

**Note: ** By default, Jenkins will not be accessible to the external world due to the inbound traffic restriction by AWS. Open port 8080 in the inbound traffic rules as show below.

COPY THE FILE FROM THE JENKINS
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

