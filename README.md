# Dockerfile 
Must have / vulture studio code and docker extensions
Create docker images with command
*******docker build -t kali******** .
docker run -h "kali-linux" -t -i -p 222:22 kali /bin/bash

In this Dockerfile you can install Tools.
FROM kalilinux / kali: latest
RUN apt-get update -y
RUN apt-get install -y nano curl git
RUN apt-get install python3-pip -y
RUN apt-get install python2.7 -y
RUN apt-get install ssh -y
RUN systemctl enable ssh
ENTRYPOINT service ssh start && bash
#COPY / etc / ssh / sshd_config sshd_config1
COPY sshd_config / etc / ssh /
ENTRYPOINT service ssh restart && bash
RUN echo "root: root" | chpasswd
