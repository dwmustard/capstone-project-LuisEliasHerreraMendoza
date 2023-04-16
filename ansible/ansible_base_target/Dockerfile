FROM ubuntu

RUN apt-get update  -y \
    && apt-get upgrade -y \ 
    && apt-get install -y \
    ssh \
    sshpass \
    sudo \
    software-properties-common

RUN curl -fsSL https://deb.nodesource.com/setup_19.x | bash - &&\
apt-get install -y nodejs


RUN useradd -rm -d /home/ansible_controller -s /bin/bash -g root -G sudo -u 1001 ansible_controller
RUN echo ansible_controller:12345 | chpasswd
RUN echo "ansible_controller ALL=(ALL:ALL) NOPASSWD: ALL" |  EDITOR="tee -a"  visudo


RUN mkdir -p /home/ansible_controller/.ssh

WORKDIR /home/ansible_controller

COPY startup.sh .

COPY . .

CMD ["/bin/bash", "/home/ansible_controller/startup.sh"]
