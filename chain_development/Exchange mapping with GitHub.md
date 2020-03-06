# 1.交易所搭建节点，同步主网区块
## 物理配置
推荐配置

1. Exchanges build nodes and synchronize MainNet blocks

Physical configuration

Recommended configuration

| 事项   | 配置说明   | 
|:----|:----|
| CPU   | Intel Xeon或者同级别处理器x4核   | 
| 内存   | DDR4 2400MHz或者同级别16G   | 
| 存储   | 1T   | 
| 带宽   | 50M   | 
| 公网IP   | 有   | 



| Item   | Configuration instructions   | 
|:----|:----|
| CPU   | Intel Xeon or equivalent processor x4 core   | 
| RAM   | DDR4 2400MHz or equivalent 16G   | 
| Storage   | 1T   | 
| Bandwidth   | 50M   | 
| Public Net IP   | Yes   | 

## 部署环境
ubuntu 16.04

## Deployment environment
ubuntu 16.04

## 安装前置条件
docker

## Installation preconditions
docker

## 运行安装脚本
curl [https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.1/build_chain.sh](https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.0.9/build_chain.sh) | bash

下载运行安装脚本，该脚本会从阿里云拉取镜像，取主网的配置文件config和genesis创世文件，并运行镜像。

该脚本启动后把日志和配置文件及区块数据映射到/mnt/witness下面，可以实时查看。

查看日志，大约几秒后会出现got block的字样.

Run the installation script

curl [https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.1/build_chain.sh](https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.1/build_chain.sh) | bash

Download and run the installation script, which will pull the image from Alibaba Cloud, take the configuration file config and genesis creation file of the MainNet, and run the image.

After the script is started, mapping the log and configuration files and block data to / mnt / witness, which can be viewed in real time. Check the log, the word got block will appear in a few seconds.

# 2.下载链钱包，连接主链操作
## 2. Download the chain wallet and connect to the main chain operation
## 1.下载钱包
[https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1](https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1)/linux

下载可用的钱包二进制文件 cli_wallet.tar.gz并解压。

1. Download wallet

 [https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1/linux](https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1/linux)

Download the available wallet binary file cli_wallet.tar.gz and unzip it.

## 2.运行钱包
进入钱包目录，运行命令

./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s wss://api.cocosbcx.net

连接主网

或是连接本地节点，只需将后面的域名修改即可。

例如：./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s ws://127.0.0.1:8049

2. Run the wallet

Enter the wallet directory and run the command

 ./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s wss: //api.cocosbcx.net

 Connect to MainNet

 or connect to the local node, just modify the domain name.

For example: ./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s ws: //127.0.0.1: 8049

# 3.钱包一般操作
可以参见官网[https://cn-dev.cocosbcx.io/docs/22-cli_wallet](https://cn-dev.cocosbcx.io/docs/22-cli_wallet)

3. General operation of wallet

Access official website to check: [https://dev.cocosbcx.io/docs/22-cli_wallet](https://dev.cocosbcx.io/docs/22-cli_wallet)

# 4.API操作
可以选择使用API与链交互，目前提供各种版本：JS、IOS、Android，Python.

具体使用说明可参见官网介绍第8章

[https://cn-dev.cocosbcx.io/docs/81-js-sdk](https://cn-dev.cocosbcx.io/docs/81-js-sdk)

参考资料：

[https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker](https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker)

[https://cn-dev.cocosbcx.io/docs](https://cn-dev.cocosbcx.io/docs/22-cli_wallet)

4.API operation

You can choose to use the API to interact with the chain. Following various versions are currently available: JS, IOS, Android, Python。

Access official website to check:[https://dev.cocosbcx.io/docs/81-js-sdk](https://dev.cocosbcx.io/docs/81-js-sdk)

For specific instructions, check Chapter 8 of the official website(english version not ready)

References:

 [https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker](https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker)

 [https://cn-dev.cocosbcx.io/docs](https://cn-dev.cocosbcx.io/docs)

