FROM ubuntu:22.04
LABEL maintainer Snowpack<support@snowpack.eu>


#COPY snowpack-network/ /root
COPY snowpack/bin /root

# Update ubuntu
RUN apt-get update

#Install packets
RUN apt-get install -y nftables
RUN apt-get install -y apt-utils
RUN apt-get install -y net-tools
RUN apt-get install -y sudo

#env variables to be used for username and password 
ENV USER user
ENV PASSWORD password

RUN ls /root
RUN cd /root

#Launch snowpack as root
#The "-mr" option allows you to select multiples routes. If you need to changes your routes by using the IP adresses or just the Country name, 
# Access the ./snowpack/config_user_routes.json file and restart the docker-compose 
ENTRYPOINT cd /root; ./snowpack-cli -m user -c config.ini -u $USER -p $PASSWORD -mr ./snowpack/config_user_routes.json
