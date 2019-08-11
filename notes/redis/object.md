## Redis对象
- 基于引用计数的内存回收机制
- 通过引用计数技术实现的对象共享技术
- redis对象有 对象类型type ,底层实现编码encoding ,指向底层数据结构的指针*ptr三个属性
#### 字符串 string
###### 编码
- raw: 长度大于32字节，长字符串,SDS
- int: 8个字节的长整型
- embstr: 长度小于32字节短字符串
###### 命令 
    SET GET APPEND INCRBYFLOAT INCRBY DECRBY STRLEN SETRANGE GETRANGE
#### 哈希 hash
###### 编码
- ziplist: 元素个数小于512且所有值小于64字节
- hashtable: 哈希表，读写复杂度为1，哈希类型不满足ziplist条件时使用
###### 命令
#### 列表 list
###### 编码
- ziplist: 元素个数小于512且所有值小于64字节
- linkedlist: 双向链表，列表类型无法满足ziplist时使用
- quicklist
###### 命令
#### 集合 set
###### 编码
- intset: 元素都是整数且个数小于512
- hashtable
###### 命令
#### 有序集合 sorted set
###### 编码
- ziplist: 元素个数小于128且每个值小于64字节，可减少内存使用
- skiplist
###### 命令 
