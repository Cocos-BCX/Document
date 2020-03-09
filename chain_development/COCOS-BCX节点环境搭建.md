# 物理配置
推荐配置

| 事项 | 配置说明 | 
|:----:|:----:|
| CPU | Intel Xeon或者同级别处理器x4核 | 
| 内存 | DDR4 2400MHz或者同级别16G | 
| 存储 | 1T | 
| 带宽 | 50M | 
| 公网IP | 有 | 

# 部署环境
ubuntu 16.04

# 安装前置条件
docker

# 运行安装脚本
curl [https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.2/build_chain.sh](https://raw.githubusercontent.com/Cocos-BCX/cocos-bcx-node-bin/master/fullnode/mainnet/v1.1.2/build_chain.sh) | bash

下载运行安装脚本，该脚本会从阿里云拉取镜像，取主网的配置文件config和genesis创世文件，并运行镜像。

该脚本启动后把日志和配置文件及区块数据映射到/mnt/witness下面，可以实时查看。

查看日志，大约几秒后会出现got block的字样.

详细可以参照wiki：[https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker](https://github.com/Cocos-BCX/cocos-mainnet/wiki/Run-With-Docker)

## 配置非出块节点
对于非出块节点，配置config.ini中seed-nodes接收IP：port即可。

运行安装脚本下载得config.ini文件不用修改,里面初始配置若干个出块节点.

# 







