# Physical configuration
Recommended configuration


| Item | Configuration instructions | 
|:----:|:----:|
| CPU | Intel Xeon or same level processor x4 core | 
| RAM | DDR4 2400MHz or same level 16G | 
| Storage | 1T | 
| Bandwidth | 50M | 
| Public IP | Yes | 

# Deployment environment
ubuntu 16.04

# Installation preconditions
docker

# Run the installation script
curl [https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.2/build_chain.sh](https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.2/build_chain.sh) | bash

Download and run the installation script, which will pull the image from Alibaba Cloud, take the MainNet configuration file config and genesis creation file, and run the image.

After the script is started, the log and configuration files and block data are mapped to / mnt / witness, which can be viewed in real-time.

Check the log, the word got block will appear in a few seconds.

For details, please check the wiki: [https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker](https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker)

## Configure non-blocking nodes
For non-blocking nodes, configure seed-nodes in config.ini to receive IP: port.

The config.ini file downloaded by running the installation script does not need to be modified, and it initially configures several block-producing nodes.

