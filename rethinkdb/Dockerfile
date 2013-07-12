# Install a rethinkdb node. The node will be accessible via HTTP on port 8100. The port can be changed.

# After creating the image you can run:
#
#    docker run -i -t rethinkdb
#
# Which will run with database storage in /var/rethinkdb on the containers file system
#
# To expose a system directory on the host:
#
#    First initialize the database directory
#
#    docker run -b /local/path:/var/rethinkdb -i -t rethinkdb create -d /var/rethinkdb/db
#
#    Then you can run new containers that access that database.
#
#    docker run -b /local/path:/var/rethinkdb -i -t rethinkdb
#
#    Just don't run multiple containers using that at the same time.
#
# This image will be created to use an entrypoint. If you need to create a container 
#   with a shell you can run:
#
#    docker run -i -t -entrypoint='/bin/bash' rethinkdb -i
#
#    Just keep in mind that's giving you a shell in a new instance of the image not 
#    connecting you to an already running container.

FROM ubuntu
MAINTAINER Kimbro Staken

RUN echo "0.2" > /version

#ADD https://raw.github.com/kstaken/dockerfile-examples/master/rethinkdb-install.sh /rethinkdb-install.sh
ADD rethinkdb-install.sh /

#RUN /bin/bash /rethinkdb-install.sh

EXPOSE 8100

#ENTRYPOINT ["rethinkdb"]

#CMD ["-d", "/var/rethinkdb/db", "--bind", "all", "--http-port", "8100"] 
