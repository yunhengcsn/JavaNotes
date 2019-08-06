## Redis对象
##### 字符串 string
1. 编码
- raw: 长字符串
- int: 8个字节的长整型
- embstr: 短字符串
2. 命令
##### 哈希 hash
1. 编码
- ziplist: 元素个数小于512且所有值小于64字节
- hashtable: 哈希表，读写复杂度为1，哈希类型不满足ziplist条件时使用
2. 命令
##### 列表 list
1. 编码
- ziplist: 元素个数小于512且所有值小于64字节
- linkedlist: 双向链表，列表类型无法满足ziplist时使用
- quicklist
2. 命令
##### 集合 set
1. 编码
- intset: 元素都是整数且个数小于512
- hashtable
2. 命令
##### 有序集合 sorted set
1. 编码
- ziplist: 元素个数小于128且每个值小于64字节，可减少内存使用
- skiplist
2. 命令 
