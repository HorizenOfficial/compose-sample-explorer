#### Requirements:
1. Install docker and docker-compose https://docs.docker.com/install/linux/docker-ce/debian/ https://docs.docker.com/compose/install/
2. `git clone https://github.com/HorizenOfficial/compose-sample-explorer && cd compose-sample-explorer`
3. Change default zend RPC user:password in .env and bitcore-node.json
4. Start with `docker-compose up -d`

#### Testnet:
1. Start with `docker-compose -f docker-compose.testnet.yml up -d`

#### Trobleshooting:

It is possible that newer versions of Docker may fail when building the image. In those cases use:
1. `docker-compose disable-v2`
2. `docker-compose up -d`
