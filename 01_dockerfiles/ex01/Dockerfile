FROM debian

MAINTAINER jronald

RUN apt-get update && apt-get install wget bzip2
RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 
RUN tar xfvj teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2 

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

#build - docker build -t ex01 .

#run docker run -d -p 9987:9987/udp -p 10011:10011 -p 30033:30033 --name=test ex01