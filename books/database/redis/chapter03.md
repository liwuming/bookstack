
redis配置文件

1、redis配置文件对配置项大小写不敏感
2、支持include标签，可以将多个配置文件合并成一个
3、network

general通用配置
daemon

loglevel notice #默认级别notice，
logfile ""
databases 16	#数据库的数量，默认是16个


持久化配置
持久化，
1、快照配置
```bash
#如果900s内至少有1个key进行了修改，则进行持久化操作
save 900 1
#如果300s内至少有10个key进行了修改，则进行持久化操作
save 300 10
#如果60s内至少有10000个key进行了修改，则进行持久化操作
save 60 10000
```

rdbcompress yes #是否压缩rdb文件，需要消耗一定的cpu资源


