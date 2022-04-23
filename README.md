<!-- 
README.md for explanation of this repository
..>

# Syslog Server
# https://hub.docker.com/r/balabit/syslog-ng/

docker pull balabit/syslog-ng

# docker run -itd -p 514:514/udp -p 601:601 --name syslog-ng balabit/syslog-ng:latest

docker run -it -p 514:514/udp -p 601:601 --name syslog-ng balabit/syslog-ng:latest -edv

# run loggen to emilate client
docker exec -it syslog-ng /bin/bash

# http://manpages.ubuntu.com/manpages/bionic/man1/loggen.1.html
# 100 messages per second wiht size of 200 bytes for 30 seconds to localhost port 514
loggen -S -P --size 200 --rate 100 --interval 30 localhost 514
