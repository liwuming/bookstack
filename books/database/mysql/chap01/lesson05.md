



对于dba来说，最基本的工作就是数据库的备份与恢复，

本章主要介绍对innodb存储引擎的备份，MySQL数据库提供了大多数的工具--mysqldump、ibbackup、replication都能很好的完成备份工作，当然也可以通过第三方工具来完成，如xtrabackup、lvm快照备份等；

# 备份的分类
根据分类的方法可以分为：
hot backup--热备
cold backup--冷备
warn backup--温备

所谓hot backup是指在数据库运行中直接备份，









二进制日志备份



快照备份



