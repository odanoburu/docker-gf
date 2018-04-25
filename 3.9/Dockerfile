FROM debian:9

RUN apt-get update \
    && apt-get install -y \
       wget \
    && rm -rf /var/lib/apt/lists/*

RUN wget -q http://www.grammaticalframework.org/download/gf_3.9-1_amd64.deb && dpkg -i gf_3.9-1_amd64.deb && rm gf_3.9-1_amd64.deb
