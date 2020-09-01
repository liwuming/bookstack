# redis的数据类型


## 字符串--string

```bash
set
setnx 存入一个不存在的字符串键值对
get 
del 删除一个字符串键值
expire key seconds 设置键在多少秒后过期

--原子加减操作
incr key
decr key
incrby key
decrby key 
``` 

使用冒号作为分隔符以此来构建命名空间




### 应用场景
计数器--阅读量
session共享





## 列表--list




### 应用场景







## 哈希--hash
hset
hget




# 数据安全与性能保障
> redis提供了





