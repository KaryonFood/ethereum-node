FROM ubuntu:xenial

LABEL Nick Vanden Eynde ninjawulf98@gmail.com

VOLUME ["/data", "/genesis"]

ENV binary=geth-alltools-linux-amd64-1.9.15-0f77f34b.tar.gz \
  gethBaseUrl=https://gethstore.blob.core.windows.net/builds \
  bootnodeport=30303 \
  syncmode="full" \
  networkid="6942" \
  gasprice="0" \
  gcmode="archive" \
  rpcapi="admin,clique,db,eth,debug,miner,net,shh,txpool,personal,web3"

RUN apt-get update \
  && apt-get install -y wget \
  && rm -rf /var/lib/apt/lists/*

WORKDIR "/miner"
COPY *.sh /usr/bin/
COPY genesis.json /genesis/genesis.json
RUN chmod +x /usr/bin/run.sh

CMD ["/usr/bin/run.sh"]

EXPOSE 8545
EXPOSE 30303
EXPOSE 30303/udp
