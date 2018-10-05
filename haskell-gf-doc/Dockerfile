FROM odanoburu/haskell-gf

RUN apt-get update \
    && apt-get install -y \
       curl \
       txt2tags \
       graphviz \
    && rm -rf /var/lib/apt/lists/*

RUN curl http://www.grammaticalframework.org/download/gf_3.9-1_amd64.deb > gf.deb && dpkg -i gf.deb && rm gf.deb

RUN git clone -b master --single-branch https://github.com/GrammaticalFramework/gf-core.git

RUN cd gf-core/src/tools/ && cabal update && cabal install

CMD ["bash"]
