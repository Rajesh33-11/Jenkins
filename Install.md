```
#!/bin/bash

# Update package list
sudo apt update -y

# Upgrade packages
sudo apt upgrade -y

# Install essential tools
sudo apt install git openjdk-8-jdk maven -y

# Install Java 17 (recommended for latest Jenkins)
sudo apt install -y openjdk-17-jdk

# Check Java version
java -version

# Add Jenkins key and repo
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
/usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

# Update again after adding Jenkins repo
sudo apt update -y

# Install Jenkins
sudo apt install -y jenkins

# Select Java version (if multiple installed)
sudo update-alternatives --config java

# Start Jenkins
sudo systemctl start jenkins

# Enable Jenkins to start on boot
sudo systemctl enable jenkins

````

# Check Jenkins status
sudo systemctl status jenkins
