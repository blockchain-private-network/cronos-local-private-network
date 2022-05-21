## Official docs

https://cronos.org/docs/getting-started/local-devnet.html#devnet-running-latest-development-node

## Overview

Use shell script to start a local development network with a single validator.

## Install cronos

```bash
git clone https://github.com/crypto-org-chain/cronos
cd cronos
make install
```

## Start script

```bash
wget https://raw.githubusercontent.com/crypto-org-chain/cronos-docs/master/docs/getting-started/assets/init_cronos_chain/init.sh
```

## Customize (optional)

You can modify the params as needed:

```bash
### customize the name of your key, the chain-id and moniker of the node ###
  KEY="mykey"
  CHAINID="cronos_777-1"
  MONIKER="localtestnet"
.......
### specify the default keyring back-backend to be 'test' for convenience ###
  cronosd config keyring-backend test
  cronosd config chain-id $CHAINID
.......
# Allocate genesis accounts (cosmos formatted addresses)
  cronosd add-genesis-account $KEY 100000000000000000000000000aphoton --keyring-backend test
# Sign genesis transaction
  cronosd gentx $KEY 1000000000000000000000aphoton --keyring-backend test --chain-id $CHAINID
```

## Start local network

```bash
bash init.sh
```
