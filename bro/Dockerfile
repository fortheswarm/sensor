#
# strcrzy/sensor:bro
# designed for use with strcrzy/sink
#
FROM blacktop/bro
MAINTAINER strcrzy, https://github.com/strcrzy

RUN apt-get -qq update && apt-get -qq install ucspi-tcp supervisor pkg-config 
RUN true
ADD /bin/bro_wrapper /nsm/bro/bin/
RUN chmod +x /nsm/bro/bin/bro_wrapper

# cleanup
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
ENV PATH /nsm/bro/bin:$PATH

ENTRYPOINT ["/nsm/bro/bin/bro_wrapper"]
CMD ["-C","-i","eth0", "local.bro"]

EXPOSE 1984 
