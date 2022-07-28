FROM jenkins/jenkins:2.346.2
USER root
RUN apt-get update && apt-get install -y ruby make git \
    && rm -rf /var/lib/apt/lists/*
USER jenkins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --plugin-file=/usr/share/jenkins/ref/plugins.txt