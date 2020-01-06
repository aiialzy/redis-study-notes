# redis-study-notes
redis学习笔记

# 增删查
* 增加: set mykey 10
* 查找: get mykey
* 删除: del mykey

# 针对数字类型
* 自增: incr mykey
* 增加: incrby mykey 2
* 增加有小数的: incrbyfloat mykey 0.1 
* 自减: decr mykey 
* 减少: decrby mykey 3
