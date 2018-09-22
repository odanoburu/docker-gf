FROM haskell:8.2.2

RUN apt-get update \
    && apt-get install -y \
       alex \
       happy \
       libghc-haskeline-dev \
    && rm -rf /var/lib/apt/lists/*

RUN cabal update && cabal install gf

CMD ["bash"]
