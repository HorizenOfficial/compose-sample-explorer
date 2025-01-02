#### Requirements:
1. Install docker https://docs.docker.com/engine/install/
2. `git clone https://github.com/HorizenOfficial/compose-sample-explorer && cd compose-sample-explorer`
3. Change default zend RPC user:password in .env and bitcore-node.json
4. Start with `docker compose up -d`

#### Testnet:
1. Start with `docker compose -f docker-compose.testnet.yml up -d`

#### Accessing insight-api:
- insight-api will be reachable under http://127.0.0.1:3001/api or http://$HOST_IP:3001/api
- note that by default the insight-api http port is exposed to the outside world at TCP port 3001
  - should this not be desired remove the `ports:` section of the insight-ui-zen service in docker-compose.yml and replace it with an `expose:` section
- for API documentation see https://github.com/HorizenOfficial/bitcore-node-zen/blob/master/docs/insight-api.yaml
