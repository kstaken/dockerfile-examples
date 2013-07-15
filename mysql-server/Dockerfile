# A very rudimentary mysql service
#
# This is intended to have mysql client run remotely. It has a default user setup as 'admin' with password 'mysql-server'
# 
# So you might run two instances of this container. One as server, then run your client in a separate temporary container.
#
# docker build -t="mysql-server" .
#
# Launch the server
#
# docker run -d mysql-server
#
# Find the IP of the server
#
# MYSQL_IP=`docker inspect CONTAINER_ID | python -c 'import json,sys;obj=json.load(sys.stdin);print obj[0]["NetworkSettings"]["IPAddress"]'`
#
# docker run -i -t mysql-server mysql -u admin -p -h $MYSQL_IP

FROM ubuntu:12.04

MAINTAINER Kimbro Staken version: 0.1

ADD ./mysql-setup.sh /tmp/mysql-setup.sh
RUN /bin/sh /tmp/mysql-setup.sh

# Adding this will expose mysql on a random host port. It's recommended to avoid this. Other containers on the same 
# host can use the service without it.
#EXPOSE 3306

CMD ["/usr/sbin/mysqld"]
