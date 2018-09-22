FROM odanoburu/hackage-gf:latest

RUN git clone -b master --single-branch https://github.com/GrammaticalFramework/gf-rgl.git; mkdir /root/gf-lib-path

ENV GF_LIB_PATH "/root/gf-lib-path"

RUN cd gf-rgl && bash Make.sh

CMD ["bash"]
