FROM ubuntu:20.04

RUN apt-get update && apt-get install -y openssh-server python3-apt cron

RUN mkdir -p /var/run/sshd

RUN echo 'root:root' | chpasswd

RUN sed -ri 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
