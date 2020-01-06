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

