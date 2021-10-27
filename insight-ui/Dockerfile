FROM node:fermium

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install git libczmq-dev python2.7-dev build-essential \
    && export NODE_ENV=production \
    && npm install -g HorizenOfficial/bitcore-node-zen#$BITCORE_NODE_ZEN_TAG --unsafe

USER node

RUN cd /home/node \
    && export NODE_ENV=production \
    && bitcore-node create zen-explorer \
    && cd zen-explorer \
    && bitcore-node install HorizenOfficial/insight-api-zen#$INSIGHT_API_TAG HorizenOfficial/insight-ui-zen#$INSIGHT_UI_TAG

WORKDIR /home/node/zen-explorer

CMD exec /bin/sh -c "bitcore-node start"

