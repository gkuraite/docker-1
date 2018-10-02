# https://www.diffen.com/difference/TCP_vs_UDP
# differences between TCP && UDP :
# TCP(Transmission Control Protocol) is connection oriented – once a connection is established, data can be sent bidirectional.
# UDP(User Datagram Protocol) is a simpler, connectionless Internet protocol.
#
# wget : stands for "web get". It is a command-line utility which downloads files over a network.
#
# Link on how to install Teamspeak on debian :
# https://www.vultr.com/docs/how-to-install-teamspeak-3-server-on-debian-9-stretch
#
# Why do you need to install bzip2 package :
# https://stackoverflow.com/questions/26958741/extract-tar-the-tar-bz2-file-error

FROM debian

EXPOSE 9987/udp
EXPOSE 30033/tcp
EXPOSE 10011/tcp

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y wget bzip2

RUN wget http://dl.4players.de/ts/releases/3.1.1/teamspeak3-server_linux_amd64-3.1.1.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.1.1.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

RUN touch .ts3server_license_accepted

#ENTRYPOINT sh ts3server_startscript.sh start
ENTRYPOINT sh ts3server_runscript.sh runscript

# To  build :
# docker build --tag ex01 .
#
# to run :
# docker run --rm --publish 9987:9987/udp --publish 10011:10011/tcp --publish 30033:3033/tcp ex01
