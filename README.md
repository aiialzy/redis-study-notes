# redis-study-notes
redis学习笔记

# 通用
* 增加/修改: set mykey 10
* 查找: get mykey
* 删除: del mykey
* 是否存在: exists mykey
* 给key换个名字: rename mykey ikey // 把`mykey`重命名为`ikey`
* 获取值的类型: type mykey
* 获取当前系统时间: time
* 根据字符串搜索当前的key: keys 'keyname'

# 针对数字类型

加法数字参数可以是负数，减法不可以

整数可以被操作为浮点数，浮点数不可以变成整数

* 自增: incr mykey
* 增加: incrby mykey 2 // 该数值可以为负数
* 增加带小数的: incrbyfloat mykey 1.1 // 该数值可以为负数
* 自减: decr mykey 
* 减少: decrby mykey 3 //该数值不可以为负数

# 针对字符串类型
* 添加: append mykey 'hello' // 如果不存在`mykey`,则创建键对值;如果已存在,则会在后面添加字符串;如果值不是字符串,则会把值变为字符串
* 获取长度: strlen mykey // 这个返回的是字符数,不是字节数
* 字符替换: setrange mykey 6 'nononono' // 从`mykey[6]`开始把字符替换为后面的字符串值,如果`mykey`在替换前字符数不足则会自动补零

# 针对hash(哈希)类型
* 设置属性: hset map username xiaohong
* 设置多个属性: hmset map username xiaohong age 18
* 获取属性: hget map username
* 获取多个属性: hmget map username age
* 获取的所有属性: hgetall map // [属性名, 属性值, 属性名, 属性值 ... ]
* 删除属性: hdel map username
* 获取属性数量: hlen map
* 获取中所有key(相当于js中的Object.keys(object)): hkeys map
* 获取中所有value(相当于js中的Object.values(object)): hvals map
* 查询中属性是否存在: hexists map username

# 针对list(列表)类型
* 左进入: lpush list 1 2 3 4 5 ...
* 右进入: rpush list 1 2 3 4 5 ...
* 根据index设置: lset 0 2
* 插入: linsert list before 1 10 // 一次只能插入一个元素
* 左弹出: lpop list
* 右弹出: rpop list
* 根据范围获取(左右边界也取): lrange list 5 10 // 数值可为负数, `-n`表示`list.length - 1 - n`
* 查看长度: llen list
* 根据索引取出元素: lindex list 5
* 删除然后添加元素: lrem list 10 2 // 当第一个数值大于0时,从左往右进行删除;小于0时,从右往左进行删除;等于0时,全部删除.删除之后再添加数据,一次只能添加一个元素
* 提取: ltrim list 0 -1

# 针对set(集合)类型
* 插入元素: sadd set 1 2 3 4 5 ...
