FROM ubuntu
MAINTAINER Kimbro Staken

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y wget sudo supervisor

RUN apt-get install -y python-software-properties 
RUN add-apt-repository ppa:saltstack/salt
RUN apt-get update

# Keep upstart from complaining
RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /bin/true /sbin/initctl

RUN apt-get install -y salt-master openssh-server 

RUN echo "root:salt-master" | chpasswd
RUN mkdir -p -m0755 /var/run/sshd

ADD ./supervisor-salt.conf /etc/supervisor/conf.d/

EXPOSE 4505 4506

CMD ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisor/supervisord.conf"]  
