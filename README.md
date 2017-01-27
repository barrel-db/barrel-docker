
## Create a docker image for barrel

From this directory:

    $ docker build -t barrel .


## Run the barrel docker image

By default, this will start a barrel database on port 7080:

    $ docker run -t barrel

Start it in console mode:

    $ docker run -t barrel console

Route the port of the Barrel docker image to host port (both on 7080):

    $ docker run -p 7080:7080 -t barrel
