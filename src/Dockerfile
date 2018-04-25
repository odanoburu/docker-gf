# official haskell image -- doesn't seem to work with stack:
FROM haskell:8.2
# this image will work with stack https://github.com/ajscholl/docker-haskell/commit/62ff8e4d28949035f65f23cf68fad774b70ebb0e

RUN apt-get update \
     && apt-get install -y \
     libghc-haskeline-dev \
     autoconf \
     automake \
     libtool \
     make \
     && rm -rf /var/lib/apt/lists/*

WORKDIR /home/gfer

COPY . /home/gfer/

RUN cabal update && cabal install --only-dependencies

RUN cd /home/gfer/src/runtime/c && \
    autoreconf -i && \
    ./configure && \
    make && \
    make install

ENV LD_LIBRARY_PATH="/usr/local/lib"

# gf itself
RUN cabal install -fserver -fc-runtime --extra-lib-dirs="/usr/local/lib"
