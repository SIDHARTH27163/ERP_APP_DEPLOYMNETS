# Use Jenkins LTS image
FROM jenkins/jenkins:lts

# Switch to root user
USER root

# Install dependencies
RUN apt-get update && \
    apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release software-properties-common

# Install Docker inside the Jenkins container
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg && \
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list && \
    apt-get update && \
    apt-get install -y docker-ce docker-ce-cli containerd.io

# Install Git
RUN apt-get install -y git

# Install Amazon Corretto JDK 21
RUN apt-get install -y wget && \
    wget -O- https://apt.corretto.aws/corretto.key | gpg --dearmor | tee /usr/share/keyrings/corretto-archive-keyring.gpg > /dev/null && \
    echo "deb [signed-by=/usr/share/keyrings/corretto-archive-keyring.gpg] https://apt.corretto.aws stable main" | tee /etc/apt/sources.list.d/corretto.list && \
    apt-get update && \
    apt-get install -y java-21-amazon-corretto-jdk

RUN usermod -aG docker jenkins

# Expose port 9090
EXPOSE 9090

# Switch back to Jenkins user
USER jenkins
