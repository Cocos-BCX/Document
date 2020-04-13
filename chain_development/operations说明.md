# 1.transfer_operation
![图片](https://uploader.shimo.im/f/acCTSxiqno8z3XTC.png!thumbnail)

## 描述
转账操作

## 参数
0--op序号

from 转账源账户

to 转账目标账户

amount 转账资产对象（mount 资产数量 asset_id 资产符号）

extensions 扩展字段

# 2.limit_order_create_operation
![图片](https://uploader.shimo.im/f/masWOsuLI3YWoFVr.png!thumbnail)

## 描述
创建限价单操作

## 参数
1--op序号

seller 订单卖方

amount_to_sell 卖出资产（amount 资产数量 asset_id 资产符号 )

min_to_receive 最低接受的资产(amount 最低接收的资产数 asset_id 卖出的资产符号 )

expiration 过期时间

fill_or_kill:如果为true，若该笔订单立即被匹配则打包进区块；如果为false，则该笔订单会保留在交易市场以匹配后续的可匹配订单。

extensions：扩展字段

# 3.limit_order_cancel_operation
![图片](https://uploader.shimo.im/f/kwNKMPxJOXUCPslh.png!thumbnail)

## 描述
 取消限价单操作

## 参数
2--op序号

fee_paying_account费用支付账户

order 订单ID

extensions：扩展字段

# 4.call_order_update_operation
![图片](https://uploader.shimo.im/f/0ynKHNa5tJAnkgqf.png!thumbnail)

## 描述
 更新限价单操作

## 参数
3--op序号

funding_account 费用支付账户

delta_collateral 此次调整仓位的差额资产（amount 资产数量 asset_id 资产符号）

delta_debt 债务增加的余额（amount 资产数量 asset_id 资产符号）

extensions 扩展字段

# 5.fill_order_operation
![图片](https://uploader.shimo.im/f/Y7371wBgQAoPGo17.png!thumbnail)

## 描述
订单匹配操作

## 参数
4--op序号

order_id  订单ID

account_id 匹配订单的账户ID

pays 此次订单匹配的付出资产 （amount 资产数量 asset_id 资产符号）

receives 此次订单匹配的接收资产 （amount 资产数量 asset_id 资产符号）

fill_price 此次订单匹配的价格 （base为基础资产 quote为引用资产）

extensions 扩展字段

# 6.account_create_operation
![图片](https://uploader.shimo.im/f/NUT1t79FTacCkS6A.png!thumbnail)

## 描述
账户创建操作

## 参数
5--op序号

registrar  注册者ID

name  账户名称

owner 账户的owner权限（ weight_threshold为权重门槛  account_auths 为账户权重数组 

key_auths为 公钥权重数组 address_auths 为地址权重数组）

active 账户的active权限 （ wegight_threshold为权重门槛  account_auths 为账户权重数组 

key_auths为 公钥权重数组 address_auths 为地址权重数组）

options 账户的附属选项 （memo_key为memo加密的公钥数组  votes该账户为哪些账户投票 extensions 扩展字段）

extensions 扩展字段

# 7. account_update_operation
![图片](https://uploader.shimo.im/f/b9kovqSTlA8KYhCT.png!thumbnail)

## 描述
账户升级操作

## 参数
6--op序号

account 更新的账户ID

extensions 扩展字段

# 8. account_upgrade_operation
![图片](https://uploader.shimo.im/f/K3rYhN0clLkGIqbq.png!thumbnail)

## 描述
账户升级操作

## 参数
7--op序号

account_to_upgrade  升级的账户ID

upgrade_to_lifetime_member  是否升级到终生会员  

extensions 扩展字段

# 9.asset_create_operation
![图片](https://uploader.shimo.im/f/Gr4iQHOQhjEnxo6B.png!thumbnail)

## 描述
资产发行op

## 参数
8--op序号

issuer 资产发行账户ID

symbol 资产发行符号

precision 精度

common_options 资产的一般选项 ( max_supply 资产的最大供应量 带5位精度market_fee_percent 市场费用百分比  max_market_fee最大市场费用 issuer_permissions 发行选项 flags 发行标识 descriptions 描述 extensions 扩展字段)

extensions 扩展字段

# 10. asset_update_operation
![图片](https://uploader.shimo.im/f/IM7unwr4SPsgLpWe.png!thumbnail)

## 描述
资产升级op

## 参数
9--op序号

issuer  资产发行者

asset_to_update 升级的资产ID

new_options 资产选项 （max_supply 资产的最大供应量 带5位精度 market_fee_percent 市场费用百分比 issuer_permissions 发行权限 flags 发行标识（控制黑白名单等） description 描述 extensions：扩展字段）

extensions：扩展字段

# 11.asset_update_restricted_operation
![图片](https://uploader.shimo.im/f/y1xOnDKSP28qhPZP.png!thumbnail)

## 描述
资产操作限制升级操作

## 参数
10--op序号

payer 资产发行者

target_asset 目标资产

isadd 若为true，则为增加限制，否则为移除限制

restricted_type 限制类型（枚举）

restricted_list 限制列表

extensions：扩展字段

# 12. asset_update_bitasset_operation
![图片](https://uploader.shimo.im/f/3n6W83HvYCAXpAHh.png!thumbnail)

## 描述
智能资产升级op

## 参数
11--op序号

issuer  智能资产发行者

asset_to_update 升级的目标资产

new_options  资产选项

feed_lifetime_sec 喂价生命周期

minimum_feeds 最小喂价

force_settlement_delay_sec 强制清算延迟

force_settlement_offset_percent 强制清算偏移百分比

maximum_force_settle_volume 最大强制清算量

short_backing_asset 做空的标的资产

extensions：扩展字段

# 13.asset_update_feed_producers_operation
![图片](https://uploader.shimo.im/f/4LOrNCq4FPw3AImU.png!thumbnail)

## 描述
修改智能资产喂价账户

## 参数
12--op序号

issuer  智能资产发行者

asset_to_update 升级的目标资产

new_feed_producers 新的喂价者数组

extensions：扩展字段

# 14. asset_issue_operation
![图片](https://uploader.shimo.im/f/fjnerm0l2NUuOUp5.png!thumbnail)

## 描述
定向发行资产

## 参数
13--op序号

issuer  资产发行者

asset_to_issue 发行的资产 （amount 数量 asset_id 资产ID）

issue_to_account 发行后的资产给谁

extensions：扩展字段

# 15. asset_reserve_operation
![图片](https://uploader.shimo.im/f/NRW0RvRmSWs6KJBE.png!thumbnail)

## 描述
放弃部分资产，指定资产将被回收，流通量减少，总量不变

## 参数
14--op序号

payer  资产发行

amount_to_reserve 回收资产（mount 资产数量 asset_id 资产符号）

extensions 扩展字段

# 16.asset_settle_operation
![图片](https://uploader.shimo.im/f/bQwJ7LwEH9cAlwAz.png!thumbnail)

## 描述
清算智能资产

## 参数
15--op序号

account 清算账户

amount 清算资产（mount 资产数量 asset_id 资产符号）

extensions 扩展字段

# 17. asset_global_settle_operation
![图片](https://uploader.shimo.im/f/UqO85WQIJPAsDWeo.png!thumbnail)

## 描述
在global_settle允许的情况下清算货币交易市场

## 参数
16--op序号

issuer 清算账户

asset_to_settle 清算资产

settle_price 清算价格（base基础资产 quote引用资产）

extensions 扩展字段

# 18. asset_publish_feed_operation
![图片](https://uploader.shimo.im/f/KnrNfOhgKPMKJhO7.png!thumbnail)

## 描述
发布资产喂价

## 参数
17--op序号

publisher 发布者

asset_id 资产ID

feed喂价结构体 （settlement_price 为清算价格结构体  ，其中base为基础资产 quote为引用资产 ）

maintenance_collateral_ratio 链抵押率

maximum_short_squeeze_ratio   最大做空抵押率

extensions 扩展字段

# 19.witness_create_operation
![图片](https://uploader.shimo.im/f/41RkUFgQJnAYUV3A.png!thumbnail)

## 描述
创建见证人操作

## 参数
18--op序号

witness_account 见证人账号

url 见证人宣传url

block_sign_key 区块签名key

# 20. witness_update_operation
![图片](https://uploader.shimo.im/f/tVk52j3Q7DILM5kl.png!thumbnail)

## 描述
更新见证人操作

## 参数
19--op序号

witness 见证人ID

witness_account 见证人账号ID

worker_status 工作状态

# 21.proposal_create_operation
![图片](https://uploader.shimo.im/f/C0wECBLBLWAJeKkA.png!thumbnail)

## 描述
创建提案操作

## 参数
20--op序号

fee_paying_account 支付费用账户

expiration_time过期时间

proposed_ops 提案ops数组

worker_status 工作状态

# 22.proposal_update_operation
![图片](https://uploader.shimo.im/f/0hKl2AOy0f02P3k2.png!thumbnail)

## 描述
更新提案操作

## 参数
21--op序号

fee_paying_account 支付费用账户

proposal 提案ID

active_approvals_to_add 添加active批准权限

active_approvals_to_remove 移除active批准权限

owner_approvals_to_add 添加owner批准权限

owner_approvals_to_remove 移除owne批准权限

key_approvals_to_add 添加理事会账户的key批准权限（自己账户的私钥）

key_approvals_to_remove移除理事会账户的key批准权限

extensions 扩展字段

# 23.proposal_delete_operation
![图片](https://uploader.shimo.im/f/OXOpxfmrnl06veev.png!thumbnail)

## 描述
删除提案操作

## 参数
22--op序号

fee_paying_account 支付费用账户

using_owner_authority 是否使用owner权限

proposal 提案ID

extensions 扩展字段

# 24.committee_member_create_operation
![图片](https://uploader.shimo.im/f/G7VrkYYixAAhpmgO.png!thumbnail)

## 描述
创建理事会操作

## 参数
23-op序号

committee_member_account 理事会成员账户ID

url 理事会对外宣传url

# 25.committee_member_update_operation
![图片](https://uploader.shimo.im/f/iJiGiE7bdmISYpPP.png!thumbnail)

## 描述
更新理事会操作

## 参数
24-op序号

committee_membert 理事会ID

committee_member_account 理事会成员账户ID

work_status 工作状态

# 26.committee_member_update_global_parameters_operation
![图片](https://uploader.shimo.im/f/Nlm0l4wY3FAmbsGJ.png!thumbnail)

## 描述
理事会更新链上运行参数操作

## 参数
25-op序号

new_parameters 新的参数

current_fees(parameters参数   sacle  规模    maximun_handling_fee最大费用)

block_interval 出块间隔 

maintenance_interval  链维护周期

maintenance_skip_skots 链维护跳过的槽位

committee_proposal_review_period 理事会 提议审核期

maximum_block_size 最大块大小

maximum_time_until_expiration 过期前的最大时间

maximum_proposal_lifetime 最大的提议生命期

maximum_asset_feed_publisher 资产最大喂价者数量

committee_number_of_election 选举中理事会的数量

maximum_authority_membership 最大授权数量

cashback_gas_period_second gas解冻时间

cashback_vb_period_seconds cocos解冻时间

cashback_vote_period_seconds  投票赎回解冻时间

witness_pay_per_block 见证人出块奖励

witness_pay_vesting_seconds 见证人奖励冻结时间 

worker_budget_per_day work每天付出的预算

account_per_fee_scale 每创建多少个账户，费用左移下面参数指定的位数

account_fee_sacle_bitshifts 和上面的参数配合使用，指定左移的位数

max_authority_depth 最大授权深度

maximum_run_time_ratio 最大运行时间百分比

maximum_run_nh_order_expiration 非同资产订单的最大失效时间

assigned_task_life_cycle 分配任务的生命循环周期

crontab_suspend_threshold 任务终止门槛

crontab_suspend_expiration任务终止过期时间

witness_candidate_freeze见证候选人冻结门槛

committee_candidate_freeze理事会候选人冻结门槛

candidate_award_budget每个链周期中候选人预算

committee_percent_of_candidate_award 理事会津贴所占候选人预算的百分比

unsuccessful_candidates_percen落选候选人占剩余预算（总预算减去上面的参数指定的部分）的百分比

extension 扩展字段

# 27.vesting_balance_create_operation
![图片](https://uploader.shimo.im/f/4ic19f8ypkU6x6I2.png!thumbnail)

## 描述
创建冻结对象，保留资金

## 参数
26-op序号

creator 创建者账户ID

owner 拥有者账户ID

amount 冻结资产（mount 资产数量 asset_id 资产符号）

policy 冻结采用的策略（0-线性返现策略 1-币天的返现策略）

# 28.vesting_balance_withdraw_operation
![图片](https://uploader.shimo.im/f/XyNEKjLQsoEJL0CM.png!thumbnail)

## 描述
领取解冻的保留资金

## 参数
27-op序号

vesting_balance 解冻对象ID

owner 拥有者账户ID

amount 冻结资产（mount 资产数量 asset_id 资产符号）

# 29.worker_create_operation
![图片](https://uploader.shimo.im/f/1UaRsu8XZm442MPL.png!thumbnail)

## 描述
工作者创建

## 参数
28-op序号

work_begin_date 工作开始时间

work_end_date  工作结束时间

daily_pay 每天工作者所得

name 名字

describe  描述

initializer  初始化构造

数组类型，第一个数字为枚举类型，表示工作者类型，具体为：

0-销毁模型 销毁核心资产，资产总量将发生线性递减。 

1-扶植模型 从储备资金池中取钱

2-废弃模型 总量不变，定向线性发行指定数量的资产到无操作权限的黑洞账户

3-增发模型 增发核心资产，资产总量将发生线性递增。 

# 30.balance_claim_operation
![图片](https://uploader.shimo.im/f/WfRTzwXWQscTyWZz.png!thumbnail)

## 描述
取回链初始化时分配的资产

## 参数
29-op序号

deposit_to_account 取回资产到哪个账户ID

balance_to_claim 取回的资产对象

balance_owner_key 拥有余额的账户公钥

total_claimed asset 类型

# 31.asset_settle_cancel_operation
![图片](https://uploader.shimo.im/f/uD7jC9Gfsjcus0RZ.png!thumbnail)

## 描述
未有实体的清算取消操作

## 参数
30-op序号

settlement 清算对象

account 清算账户

amount 清算资产对象 （mount 资产数量 asset_id 资产符号） 

extensions 扩展字段

# 32. asset_claim_fees_operation
![图片](https://uploader.shimo.im/f/ifEDO426r6UIXc0N.png!thumbnail)

## 描述
资产发行人从资产累计池中取回资产

## 参数
31-op序号

issuer 发行人账户ID

amount_to_claim 资产对象 （mount 资产数量 asset_id 资产符号）  

extensions 扩展字段

# 33.bid_collateral_operation
![图片](https://uploader.shimo.im/f/ogyIqAEqZBfOkr7e.png!thumbnail)

## 描述
智能货币抵押投标

## 参数
32-op序号

bidder 抵押投票账户ID

additional_collateral 抵押资产  （mount 资产数量 asset_id 资产符号）  

debt_covered  接管的债务资产（mount 资产数量 asset_id 资产符号）  

extensions 扩展字段

# 34.execute_bid_operation
![图片](https://uploader.shimo.im/f/HQSbV0occPw4snbA.png!thumbnail)

## 描述
智能货币抵押投标

## 参数
33-op序号

bidder 抵押投票账户ID

debt 债务资产 （mount 资产数量 asset_id 资产符号）

collateral 抵押资产（mount 资产数量 asset_id 资产符号） 

extensions 扩展字段

# 35.contract_create_operation
![图片](https://uploader.shimo.im/f/kLI6GOkkxIABU8iv.png!thumbnail)

## 描述
创建合约操作

## 参数
34-op序号

owner 合约拥有者ID

name 合约名称

data 合约数据

contract_authority 合约权限

extensions 扩展字段

# 36.call_contract_function_operation
![图片](https://uploader.shimo.im/f/moqQgHDzfIIGXwcc.png!thumbnail)

## 描述
调用合约函数操作

## 参数
35-op序号

caller 合约调用者ID

contract_id 合约ID

function_name 函数名称

value_list参数列表

extensions 扩展字段

# 37.temporary_authority_change_operation
![图片](https://uploader.shimo.im/f/sNkLG0NSNiAtBaha.png!thumbnail)

## 描述
修改账户的临时权限操作

## 参数
36-op序号

owner 账户拥有者ID

describe 描述

temporary_active 临时的active权限

expiration_time 临时权限过期时间

extensions 扩展字段

# 38.register_nh_asset_creator_operation
![图片](https://uploader.shimo.im/f/q8uwBFY8kVHzz9Nj.png!thumbnail)

## 描述
注册nh资产创建者操作

## 参数
37-op序号

fee_paying_account 费用支付账户ID

# 39.create_world_view_operation
![图片](https://uploader.shimo.im/f/KAzMQsEiuwgnmuMd.png!thumbnail)

## 描述
创建世界观操作

## 参数
38-op序号

fee_paying_account 费用支付账户ID

world_view 世界观

# 40.relate_world_view_operation
![图片](https://uploader.shimo.im/f/1Ur2GdSXGF5UNKx6.png!thumbnail)

## 描述
关联世界观操作

## 参数
39-op序号

related_account 关联账户ID

world_view 世界观

vier_owner 世界观拥有者

# 41.create_nh_asset_operation
![图片](https://uploader.shimo.im/f/EJqYgjvR3qILMKwo.png!thumbnail)

## 描述
创建非同质资产操作

## 参数
40-op序号

fee_paying_account 费用支付账户ID

owner 资产拥有者

asset_id 资产ID

world_view 世界观

base_describe 基本描述

# 42.delete_nh_asset_operation
![图片](https://uploader.shimo.im/f/OnuRG2fNiImmUO4g.png!thumbnail)

## 描述
删除非同质资产操作

## 参数
41-op序号

fee_paying_account 费用支付账户ID

nh_asset 非同质资产ID

# 43.transfer_nh_asset_operation
![图片](https://uploader.shimo.im/f/6ALKQuyyPkkUT5Ff.png!thumbnail)

## 描述
转移非同质资产操作

## 参数
42-op序号

from  非同质资产的来源账户

to 非同质资产的去向账户

nh_asset 非同质资产ID

# 44.create_nh_asset_order_operation
![图片](https://uploader.shimo.im/f/IPrk4eokYIc95Im7.png!thumbnail)

## 描述
创建出售单操作

## 参数
43-op序号

seller 卖出非同质资产账号ID

otcaccount 中间的OTC账户

pending_orders_fee 出售单排队费用（mount 资产数量 asset_id 资产符号）

nh_asset 非同质资产

memo 备注

price 出售单价格（mount 资产数量 asset_id 资产符号）

expiration 过期时间

# 45.cancel_nh_asset_order_operation
![图片](https://uploader.shimo.im/f/VkTEdnYfJvkVegD6.png!thumbnail)

## 描述
取消出售单操作

## 参数
44-op序号

order 非同质资产订单ID

fee_paying_account 费用支付账户

expiration 过期时间

# 46.fill_nh_asset_order_operation
![图片](https://uploader.shimo.im/f/po0JmCXvZEx3GxNt.png!thumbnail)

## 描述
匹配非同质资产订单操作

## 参数
45-op序号

order 非同质资产订单ID

fee_paying_account 费用支付账户

seller 卖出订单ID

nh_asset 非同质资产ID

price_amount 价格数量

price_asset_id 价格资产ID

price_asset_symbol 价格资产符号

expiration 过期时间

# 47.create_file_operation
![图片](https://uploader.shimo.im/f/StfTGy1EgIE8ba5i.png!thumbnail)

## 描述
创建文件操作

## 参数
46-op序号

file_owner 文件拥有者

file_name 文件名称

file_content 文件内容

# 48.add_file_relate_account_operation
![图片](https://uploader.shimo.im/f/cBfzJ9BO0tYNSgQd.png!thumbnail)

## 描述
添加文件关联账户操作

## 参数
47-op序号

file_owner 文件拥有者

file_id 文件名称

related_account 关联账户

# 49.file_signature_operation
![图片](https://uploader.shimo.im/f/XPTvwCRPr6EYaphL.png!thumbnail)

## 描述 
文件签名操作

## 参数
48-op序号

signature_account 签名账户

file_id 文件名称

related_account 关联账户

# 50.relate_parent_file_operation
![图片](https://uploader.shimo.im/f/fruNvA42NK0RuRW5.png!thumbnail)

## 描述 
关联父文件操作

## 参数
49-op序号

sub_file_owner 子文件关联父文件操作

parent_file 父文件ID

parent_file_owner 父文件拥有者ID

sub_file 子文件ID

# 51.revise_contract_operation
![图片](https://uploader.shimo.im/f/AXnoRFqw0Nv3S4yp.png!thumbnail)

## 描述 
更新合约操作

## 参数
50-op序号

reviser 更新者账户ID

contract_id  更新合约ID

data 更新内容

extensions 扩展字段

# 52.crontab_create_operation
![图片](https://uploader.shimo.im/f/ap5ctSAcuEeYg3Wi.png!thumbnail)

## 描述 
延迟任务创建操作

## 参数
51-op序号

crontab_creator 延迟任务创建者账户ID

contract_id  更新合约ID

data 更新内容

extensions 扩展字段

# 53.crontab_cancel_operation
![图片](https://uploader.shimo.im/f/5R0OBYlMbosmXCqE.png!thumbnail)

## 描述 
延迟任务取消操作

## 参数
52-op序号

fee_paying_account 费用支付账户ID

task 任务ID

extensions 扩展字段

# 54.crontab_recover_operation
![图片](https://uploader.shimo.im/f/lq34459CukglNI8L.png!thumbnail)

## 描述 
延迟任务恢复操作

## 参数
53-op序号

crontab_owner  延迟任务拥有者

crontab 延迟任务ID

restart_time 延迟任务重启时间

extensions 扩展字段

# 55.update_collateral_for_gas_operation
![图片](https://uploader.shimo.im/f/150IE6hOAp59fWv2.png!thumbnail)

## 描述 
抵押gas操作

## 参数
54-op序号

mortgager 抵押人账户ID

beneficinary 受益人账户ID

collateral 抵押数量

# 56.account_authentication_operation
![图片](https://uploader.shimo.im/f/Ek5gpaWIsObIKKhG.png!thumbnail)

## 描述 
账户授权操作

## 参数
55-op序号

account_id 账户ID

data 数据

extensions 扩展字段

# 57.contract_share_fee_operation
![图片](https://uploader.shimo.im/f/tXUfOtm49yoVCvk2.png!thumbnail)

## 描述 
合约费用分担操作

## 参数
56-op序号

sharer  费用承担者账户ID

total_share_fee 总计分担的费用

amounts 分担的费用资产明细

