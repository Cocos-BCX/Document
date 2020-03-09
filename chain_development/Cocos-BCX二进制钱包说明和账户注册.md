# 背景
目前只提供通过手机钱包注册便宜账户，所以对于某些特殊账号名可能会提示错误。

# 一般操作
主网钱包直接创建，对于某些名字可能提示不能创建（目前钱包客户端免费创建普通账户名，某些帐户名可能并不支持创建），这时需要让技术人员协助解决。

# 流程
## 1.创建主账号交付
技术人员给出创建主账号

## 2.下载钱包
去https://github.com/Cocos-BCX/cocos-bcx-node-bin/tree/master/cli/mainnet/v1.1.1/linux

下载可用的钱包二进制文件 cli_wallet.tar.gz并解压。

## 3.运行钱包
进入钱包目录，运行命令

./cli_wallet --chain-id '6057d856c398875cac2650fe33caef3d5f6b403d184c5154abbff526ec1143c4' -s wss://api.cocosbcx.net 

连接主网

## 4.设置钱包
连接主网进入钱包后，依次键入命令如下：

1.set_password 123456 回车

2.unlock 123456 回车

注：第一次运行钱包，提示符为"new>>",按照上述设置密码解锁。

如果不是第一次运行钱包，提示符为"lock>>"，只需要进行第二步解锁即可。

## 5.生成账号公私钥
键入命令suggest_brain_key 

返回类似如下

unlocked >>> suggest_brain_key

suggest_brain_key

{

  "brain_priv_key": "ZERO SCRAPER SLENT EYELET ABRADER YARETA DRYFOOT MUCUS UNVOTE ABKARI SPANCEL DUCAPE VERMIAN LAPSED LISTING GARTER",

  "wif_priv_key": "5JgVXvBuEfU45YeiAvb9SDFagdo7HfWqGzyUNdqBqC4fjFAWvy1",

  "address_info": "COCOSK5sL9FjY7NCQFMwqeuQ5JidYGXuMRupB1",

  "pub_key": "COCOS6NkW1bTtXKSfovFsvSwxDRSRrkoVvdx5zXDQvyZ5aypQpviGfp"

}	 

## 6.注册账户
在钱包键入命令

1.register_account  欲创建的帐户名 帐户公钥 帐户公钥  欲创建账号的属主账号名称 true 

 2.import_key 欲创建的帐户名 欲创建的主帐户私钥  

# 附录：
官网二进制钱包操作命令：

[https://cn-dev.cocosbcx.io/docs/22-cli_wallet](https://cn-dev.cocosbcx.io/docs/22-cli_wallet)












# 
