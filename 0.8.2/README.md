
## Create a docker image for barrel

From this directory:

    $ docker build -t barrel .


## Push it to docker hub

The procedure to push your barrel image to docker hub is [described here](https://docs.docker.com/engine/getstarted/step_six/).

Example:

    $ docker images
    $ docker tag a6ce60ff48b5 barrel/barrel:0.8.2
    $ docker tag a6ce60ff48b5 barrel/barrel:latest
    $ docker images
    $ docker login
    $ docker push barrel/barrel

## Run the barrel docker image

By default, this will start a barrel database on port 7080:

    $ docker run -t barrel

Start it in console mode:

    $ docker run -t barrel console

Route the port of the Barrel docker image to host port (both on 7080):

    $ docker run -p 7080:7080 -t barrel

## Usage

Start as detached (background) process named *test-barrel*
from the [Docker Hub image](https://hub.docker.com/r/barrel/barrel/):

    $ docker run --detach --name=test-barrel barrel/barrel

Display the log:

    $ docker logs test-barrel

Stop the container:

    $ docker stop test-barrel

Open a bash session in the container:

    $ docker exec -it test-barrel bash

Open a remote console with the Erlang VM:

    $ docker exec -it test-barrel /barrel/bin/barrel remote_console
