Some basic dockerfile examples
==============================

Use with Docker http://www.docker.io

To build an image with docker is pretty simple:

    docker build -t="rethinkdb" - < rethinkdb.docker

Then to run that image:

    docker run -i -t rethinkdb
    