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

RUN apt-get install -y salt-minion 

ADD ./supervisor-salt.conf /etc/supervisor/conf.d/

RUN echo 'master: salt-master.local' > /etc/salt/minion

CMD ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisor/supervisord.conf"]  
