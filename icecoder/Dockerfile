
FROM ubuntu:12.04

RUN apt-get update
RUN apt-get install -y apache2 php5 libapache2-mod-php5 unzip

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

EXPOSE 80

ADD http://icecoder.net/download-zip?version=3.0beta /var/www/icecoder.zip

RUN cd /var/www && unzip -o  icecoder.zip 
RUN cd /var/www && mv ICEco* icecoder
RUN chown www-data -R /var/www/icecoder/lib /var/www/icecoder/backups /var/www/icecoder/test 
RUN mkdir /var/www/projects && chown -R www-data /var/www/projects && chmod g+s /var/www/projects

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"] 
