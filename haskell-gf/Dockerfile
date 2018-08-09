FROM haskell:8.2.2

RUN apt-get update \
    && apt-get install -y \
       curl \
    && rm -rf /var/lib/apt/lists/*

RUN curl http://www.grammaticalframework.org/download/gf_3.9-1_amd64.deb > gf.deb && dpkg -i gf.deb && rm gf.deb

CMD ["bash"]
