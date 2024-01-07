FROM ubuntu:20.04

EXPOSE 22
# CMD ["/usr/sbin/init", "&&", "systemctl", "start", "docker"]
CMD ["/usr/sbin/init"]

RUN apt-get update && \
    apt-get install -y ssh net-tools

# install docker
# RUN apt-get update && \
#     apt-get install -y ca-certificates curl gnupg && \
#     curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \
#     chmod a+r /etc/apt/keyrings/docker.gpg && \
#     echo \
#         "deb [arch=$(dpkg --print-architecture)] https://download.docker.com/linux/ubuntu \
#         $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
#         tee /etc/apt/sources.list.d/docker.list > /dev/null && \
#     apt-get update && \
#     apt install -y docker-ce docker-ce-cli containerd.io

# RUN apt-get install -y docker.io

# authorize SSH connection with root account
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config

# change password root
RUN echo 'root:Docker!' | chpasswd

WORKDIR /root

COPY ./Dockerfile.tomcat .
