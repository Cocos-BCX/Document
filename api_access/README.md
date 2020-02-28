# 链api和api-access
## 链支持的api模块
``` text
["login",0],
["block",1],
["network_broadcast",2],
["database",3],
["history",4],
["network_node",5],
["asset",6],
["debug",7]
```
每个api模块都是独立的部分，模块下有具体的api function，可供用户调用。  

节点默认权限为空，connect login时用户名和密码为空，也即不需要填写。有些api模块下的api function需要配置login的user和password后才可使用。  

配置项以json文件的形式。 下面会对配置和使用进行说明。  

### api-access 

1. api-access 在config.ini文件或命令行参数中配置。默认为空。    

2. api-access若为空，login时: user="", password=""。这种模式下，节点只开放如下4种接口：  
``` text
        database_api
        network_broadcast_api
        history_api
        network_node_api
```

3. api-access配置示例和ws连接测试    
> apiaccess.json   示例：

``` json  
{
    "permission_map":[
        [
            "root", {
                "password_hash_b64":"iHLgVGD7iiZXrFLRNH9GAF4mNqLO6OwvK0b2XZ6U1VI=",
                "password_salt_b64":"DXobg1wQ0Lg=",
                "allowed_apis":[
                    "database_api",
                    "network_broadcast_api",
                    "history_api",
                    "network_node_api",
                    "block_api",
                    "asset_api",
                    "debug_api",
                    "login_api"
                ]
            }
        ],
        [
            "*", {
                "password_hash_b64":"*",
                "password_salt_b64":"*",
                "allowed_apis":[
                    "database_api",
                    "network_broadcast_api",
                    "history_api",
                    "network_node_api"
                ]
            }
        ]
    ]
}
```

启动节点：

```shell
./witness_node --genesis-json genesis.json -d witness_node_data_dir --plugins "debug_witness account_history market_history" --api-access "apiaccess.json"
```

使用cli_wallet测试连接：

``` shell
./cli_wallet --chain-id 9f487f4cca8ababac23d3806a901e9044ab4d82be33cf2abb5cc3185e04fbafd -s ws://127.0.0.1:8052 -u root -p 123456

./cli_wallet --chain-id 9f487f4cca8ababac23d3806a901e9044ab4d82be33cf2abb5cc3185e04fbafd -s ws://127.0.0.1:8052 
```



​	a. user="root", password="123456"测试

```json
Logging RPC to file: logs/rpc/rpc.log
850251ms th_a       main.cpp:131                  main                 ] key_to_wif( committee_private_key ): 5KCBDTcyDqzsqehcb52tW5nU6pXife6V2rX9Yf7c3saYSzbDZ5W 
850251ms th_a       main.cpp:135                  main                 ] nico_pub_key: COCOS7yE9skpBAirth3eSNMRtwq1jYswEE3uSbbuAtXTz88HtbpQsZf 
850251ms th_a       main.cpp:136                  main                 ] key_to_wif( nico_private_key ): 5KAUeN3Yv51FzpLGGf4S1ByKpMqVFNzXTJK7euqc3NnaaLz1GJm 
850253ms th_a       main.cpp:183                  main                 ] wdata.ws_server: ws://127.0.0.1:8052 
850256ms th_a       main.cpp:188                  main                 ] wdata.ws_user: root wdata.ws_password: 123456 
Please use the set_password method to initialize a new wallet before continuing
new >>> info
info
{
  "head_block_num": 0,
  "head_block_id": "0000000000000000000000000000000000000000",
  "head_block_age": "48 weeks ago",
  "next_maintenance_time": "50 years ago",
  "chain_id": "9f487f4cca8ababac23d3806a901e9044ab4d82be33cf2abb5cc3185e04fbafd",
  "participation": "100.00000000000000000",
  "active_witnesses": [
    "1.6.1",
    "1.6.2",
    "1.6.3",
    "1.6.4",
    "1.6.5",
    "1.6.6",
    "1.6.7",
    "1.6.8",
    "1.6.9",
    "1.6.10",
    "1.6.11"
  ],
  "active_committee_members": []
}
new >>> 
```

b.  user="", password=""测试

```json
Logging RPC to file: logs/rpc/rpc.log
825920ms th_a       main.cpp:131                  main                 ] key_to_wif( committee_private_key ): 5KCBDTcyDqzsqehcb52tW5nU6pXife6V2rX9Yf7c3saYSzbDZ5W 
825920ms th_a       main.cpp:135                  main                 ] nico_pub_key: COCOS7yE9skpBAirth3eSNMRtwq1jYswEE3uSbbuAtXTz88HtbpQsZf 
825920ms th_a       main.cpp:136                  main                 ] key_to_wif( nico_private_key ): 5KAUeN3Yv51FzpLGGf4S1ByKpMqVFNzXTJK7euqc3NnaaLz1GJm 
825922ms th_a       main.cpp:183                  main                 ] wdata.ws_server: ws://127.0.0.1:8052 
825925ms th_a       main.cpp:188                  main                 ] wdata.ws_user:  wdata.ws_password:  
Please use the set_password method to initialize a new wallet before continuing
new >>> info
info
{
  "head_block_num": 0,
  "head_block_id": "0000000000000000000000000000000000000000",
  "head_block_age": "48 weeks ago",
  "next_maintenance_time": "50 years ago",
  "chain_id": "9f487f4cca8ababac23d3806a901e9044ab4d82be33cf2abb5cc3185e04fbafd",
  "participation": "100.00000000000000000",
  "active_witnesses": [
    "1.6.1",
    "1.6.2",
    "1.6.3",
    "1.6.4",
    "1.6.5",
    "1.6.6",
    "1.6.7",
    "1.6.8",
    "1.6.9",
    "1.6.10",
    "1.6.11"
  ],
  "active_committee_members": []
}
new >>> 
```

 