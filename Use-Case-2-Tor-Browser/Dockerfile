FROM ubuntu

LABEL maintainer = "Snowpack <support@snowpack.eu>"


ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get install -y x11-apps
RUN apt-get install -y torbrowser-launcher zenity

RUN apt-get install -y wget xz-utils


WORKDIR /home/tor
RUN wget https://www.torproject.org/dist/torbrowser/12.0.4/tor-browser-linux64-12.0.4_ALL.tar.xz
RUN tar -xvf tor-browser-linux64-12.0.4_ALL.tar.xz
RUN rm *.tar.xz


RUN useradd -ms /bin/bash toruser
RUN chown toruser:toruser -R tor-browser
USER toruser

WORKDIR /home/toruser/tor

CMD [ "/bin/bash" , "-c", "/home/tor/tor-browser/Browser/start-tor-browser" ]
