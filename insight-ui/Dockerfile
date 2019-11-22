FROM node:erbium-alpine

MAINTAINER cronic@zensystem.io

RUN echo '@edgecommunity http://dl-cdn.alpinelinux.org/alpine/edge/community' >> /etc/apk/repositories \
    && apk --no-cache add tini@edgecommunity zeromq-dev git python build-base \
    && export NODE_ENV=production \
    && npm install -g ZencashOfficial/bitcore-node-zen --unsafe

USER node

RUN cd /home/node \
    && export NODE_ENV=production \
    && bitcore-node create zen-explorer \
    && cd zen-explorer \
    && bitcore-node install ZencashOfficial/insight-ui-zen ZencashOfficial/insight-api-zen

WORKDIR /home/node/zen-explorer

ENTRYPOINT ["/sbin/tini", "-e 143", "--"]

CMD ["bitcore-node", "start"]

