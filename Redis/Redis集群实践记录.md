# Redis学习记录

## Redis主从搭建记录

环境准备：windows、mac两台机器  

主从安排计划：windows机器启动两个redis服务，mac机器启动一个redis服务

eg：windows ip-192.168.31.32  port-6379(master)  
            ip-192.168.31.32  port-6380(slave)         
    mac     ip-192.168.31.39  port-6379(slave)  
    
    
操作步骤：基于最基本的redis配置文件，依次为三个节点创建对应的配置文件redis.conf
      
redis-master.conf    bind 192.168.31.32 port 6379  
redis-slave01.conf   bind 192.168.31.32 port 6380  
redis-slave02.conf   bind 192.168.31.39 port 6379  


redis-server redis-master.conf  
redis-server redis-slave01.conf  
redis-server redis-slave02.conf  

redis-cli -h ip -p port -a password  


三个redis服务全部启动后，slave节点开始同步主节点的数据，其中主节点可读可写，但是从节点只读。

主节点挂掉之后，从节点无法主动升级（非哨兵模式下）

















# 一级标题

## 二级标题

### 三级标题

#### 四级标题

##### 五级标题

###### 六级标题

段落换行  
新一行开始

新一行
换行失败

*斜体文字*  
**字体加粗**  
***斜体文字同时加粗***  


## 列表
+ 第一项
+ 第二项
+ 第三项

- 第一项
- 第二项
- 第三项

* 第一项
* 第二项
* 第三项

1. 第一行
2. 第二行
3. 第三行  

+ 第一行
	- 子项
	- 子项
+ 第二行
	+ 子项
	+ 子项


1. 第一行
	+ 子项
	+ 子项
2. 第二行
	+ 子项
	+ 子项


## 列表和区块

> 区块开始  
> qukai  
> qukai  
> 区块结束

> 区块中加入列表  
> + 第一项
> + 第二项
> + 第三项  
> + 区块结束

+ 第一行
	> 区块开始  
	> 区块
+ 第二行  
	> 区块开始  
	> 区块

## 代码
	public static void main() {
    	System.out.println("hello markdown);
    }
    public void test() {
    	System.out.println("hello);
    }
    
    
```java
public static void main() {
	System.out.println("hello markdown");
}

public void test() {
	System.out.println("test");
}

```

## 链接  

[MarkDown 语法学习](https://www.runoob.com)

这是一个链接 [菜鸟教程](https://www.runoob.com)

[MarkDown在线编辑](http://jbt.github.io/markdown-editor/)


## 图片
![样例图](http://bb2021.cn/154b792bc3c84a3baec1c0e0a737676e)


## 表格

| 表头 | 表头 | 表头 |
| :-- | :--: | --: |
| test |test | test |
|   jjjjjjlllllllllllllllllllllllll  | lllllllllllllllllllllllllllllllllllllllllllllll| lloloksosoksoskoskso|


## 字符转义


\*文本斜体\*  
\*\*文本加粗\*\*  
\*\*\*文本斜体并且加粗\*\*\*






    






























