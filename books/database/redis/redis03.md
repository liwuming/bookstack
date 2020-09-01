
# 查看所有keys
keys *


# 列表--list
lpush
lpushx:当且仅当列表存在时，从列表左侧插入值
rpush
lpop
rpop
llen
lreg
lindex
lrange


## 高级命令
1、rpoppush source destination
命令rpoppush是在一个原子时间内，执行以下两个动作的事务：
1、将列表source中的最后一个元素弹出，并返回给客户端
2、将source弹出的元素插入到列表

brpoppush



基于redis的定时任务队列
1、下单后超过30分钟未支付，取消订单
2、


