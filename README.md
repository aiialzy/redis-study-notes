# redis-study-notes
redis学习笔记

# 增删查
* 增加: set mykey 10
* 查找: get mykey
* 删除: del mykey

# 针对数字类型 
加法数字参数可以是负数，减法不可以
整数可以被操作为浮点数，浮点数不可以变成整数
* 自增: incr mykey
* 增加: incrby mykey 2 // 该数值可以为负数
* 增加带小数的: incrbyfloat mykey 1.1 // 该数值可以为负数
* 自减: decr mykey 
* 减少: decrby mykey 3 //该数值不可以为负数
