FROM kalilinux/kali-rolling:latest
LABEL maintainer Snowpack<support@snowpack.eu>


#Upgrade Kali
RUN apt update -q --fix-missing  
RUN apt upgrade -y

#Installing packages
RUN apt install -y iptables 
RUN apt install kali-tools-top10 -y
RUN apt-get install -y wget xz-utils
RUN apt-get install nano
RUN apt-get install -y python3 python3-stem python3-pip cython3
RUN apt-get install -y gcc build-essential
RUN pip install packaging

#Clone the torghost repo from github
RUN git clone https://github.com/SusmithKrishnan/torghost.git


WORKDIR "torghost"

#Add the right to execute the build.sh script to be able to run torghost
RUN chmod +x build.sh
 
#Run the build.sh script to 
RUN ./build.sh; exit 0


