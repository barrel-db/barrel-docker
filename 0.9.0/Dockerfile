FROM erlang:20.0
LABEL description="Barrel-db docker image"

RUN apt-get update -y && apt-get install -y g++-4.9

RUN mkdir /src
RUN cd /src && git clone https://gitlab.com/barrel-db/barrel-platform.git

RUN cd /src/barrel-platform && \
    git checkout tags/0.9.0 && \
    make rel

RUN cp -r /src/barrel-platform/_build/prod/rel/barrel /

EXPOSE 7080

VOLUME ["/barrel/data", "/barrel/log"]

ENTRYPOINT ["/barrel/bin/barrel"]

# Start in foreground mode to avoid exiting docker image
CMD ["foreground"]
