FROM ubuntu:22.04

LABEL maintainer="Snowpack <support@snowpack.eu>"


ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get install -y weston zenity wget xz-utils nano \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*  

WORKDIR /home/tor
RUN wget https://www.torproject.org/dist/torbrowser/14.0a4/tor-browser-linux-x86_64-14.0a4.tar.xz
RUN tar -xvf tor-browser-linux-x86_64-14.0a4.tar.xz
RUN rm *.tar.xz


RUN useradd --uid 1000 --shell /bin/bash --create-home toruser
RUN chown -R toruser:toruser /home/tor

USER toruser

WORKDIR /home/tor/tor-browser/Browser

CMD ["./start-tor-browser"]

EXPOSE 6000
