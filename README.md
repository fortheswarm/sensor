sensor
======

Dockerfiles for popular open source IDS software

included:

- bro
- suricata

coming soon:

- snort

usage
-----
attach this container to a running container with the `--net=container:<container id>` flag.

sink your logs to a [`sink`](https://github.com/fortheswarm/sink) container with `--volumes-from=<sink container>`.

don't forget to pass either `--cap-add=NET_RAW --cap-add=NET_ADMIN` or `--privileged`, or the sensor will not work!


example:

`docker run --cap-add=NET_RAW --cap_add=NET_ADMIN -d --volumes-from=sink --net=container:<container to tap> strcrzy/sensor:bro`
