FROM docker:dind

# authorize SSH connection with root account
# RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config

# change password root
RUN echo 'root:Docker!' | chpasswd

WORKDIR /root
COPY ./Dockerfile.tomcat Dockerfile
