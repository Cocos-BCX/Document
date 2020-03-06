# 1. Exchanges build nodes and synchronize MainNet blocks
## Physical configuration
Recommended configuration

| Item   | Configuration instructions   | 
|:----|:----|
| CPU   | Intel Xeon or equivalent processor x4 core   | 
| RAM   | DDR4 2400MHz or equivalent 16G   | 
| Storage   | 1T   | 
| Bandwidth   | 50M   | 
| Public Net IP   | Yes   | 

## Deployment environment
ubuntu 16.04

## Installation preconditions
docker

Run the installation script

curl [https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.1/build_chain.sh](https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.1/build_chain.sh) | bash

Download and run the installation script, which will pull the image from Alibaba Cloud, take the configuration file config and genesis creation file of the MainNet, and run the image.

After the script is started, mapping the log and configuration files and block data to / mnt / witness, which can be viewed in real time. Check the log, the word got block will appear in a few seconds.

# 2. Download the chain wallet and connect to the main chain operation
1. Download wallet

 [https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1/linux](https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1/linux)

Download the available wallet binary file cli_wallet.tar.gz and unzip it.

## 2. Run the wallet
Enter the wallet directory and run the command

 ./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s wss: //api.cocosbcx.net

 Connect to MainNet

 or connect to the local node, just modify the domain name.

For example: ./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s ws: //127.0.0.1: 8049

# 3. General operation of wallet
Access official website to check: [https://dev.cocosbcx.io/docs/22-cli_wallet](https://dev.cocosbcx.io/docs/22-cli_wallet)

# 4.API operation
You can choose to use the API to interact with the chain. Following various versions are currently available: JS, IOS, Android, Python。

Access official website to check:[https://dev.cocosbcx.io/docs/81-js-sdk](https://dev.cocosbcx.io/docs/81-js-sdk)

For specific instructions, check Chapter 8 of the official website(english version not ready)

References:

 [https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker](https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker)

 [https://cn-dev.cocosbcx.io/docs](https://cn-dev.cocosbcx.io/docs)

