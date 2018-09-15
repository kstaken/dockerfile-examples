FROM ubuntu
MAINTAINER Kimbro Staken

RUN apt-get update
RUN apt-get --yes install software-properties-common python curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get update
RUN apt-get --yes install nodejs
RUN mkdir /var/www

ADD app.js /var/www/app.js

CMD ["/usr/bin/node", "/var/www/app.js"]
