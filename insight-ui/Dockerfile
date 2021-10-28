FROM node:fermium

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install git libczmq-dev python2.7-dev build-essential \
    && export NODE_ENV=production \
    && npm install -g HorizenOfficial/bitcore-node-zen#v4.0.0 --unsafe

USER node

RUN cd /home/node \
    && export NODE_ENV=production \
    && bitcore-node create zen-explorer \
    && cd zen-explorer \
    && bitcore-node install HorizenOfficial/insight-api-zen#v1.0.0 HorizenOfficial/insight-ui-zen#v0.4.0

WORKDIR /home/node/zen-explorer

CMD exec /bin/sh -c "bitcore-node start"

