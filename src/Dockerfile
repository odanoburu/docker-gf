# official haskell image -- doesn't seem to work with stack:
FROM haskell:8.2.2
# this image will work with stack https://github.com/ajscholl/docker-haskell/commit/62ff8e4d28949035f65f23cf68fad774b70ebb0e

RUN apt-get update \
     && apt-get install -y \
     happy \
     alex \
     libghc-haskeline-dev \
     autoconf \
     automake \
     libtool \
     make \
     && rm -rf /var/lib/apt/lists/*

WORKDIR /home/gfer

RUN cabal update && cabal install gf -fserver -fc-runtime --only-dependencies

ENV LD_LIBRARY_PATH="/usr/local/lib"
