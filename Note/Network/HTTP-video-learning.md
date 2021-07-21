# HTTP学习笔记

创建日期：2020.11.20 22：15 

视频链接：https://www.bilibili.com/video/BV1CK4y1t7pR?p=2



# ==Day 01== 2020.11.20 22:15

打电话：DNS对应通讯录，号码对应IP地址，交流的语言对应HTTP协议

![image-20201120223036446](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201120223036446.png)

22：40 pause 进度 P2结束。



# ==Day 02==

2020.11.22 13：20

### 1.HTTP协议的诞生历程

#### 1.1990年提出

蒂姆伯纳斯，在1990年提出了HTTP协议：完成了万维网3大基础的设计：命名方案URI，通信协议HTTP，标记语言：HTML。并实现了一个webSever（ CREN HTTPD)和浏览器（万维网**（英语：World Wide Web ）亦作**WWW**、**Web，是一个透过[互联网](https://zh.wikipedia.org/wiki/互联网)访问的，由许多互相链接的[超文本](https://zh.wikipedia.org/wiki/超文本)组成的系统[[1\]](https://zh.wikipedia.org/wiki/万维网#cite_note-1) ）

年底 第一个网页,在CERN内部已经可以访问：

 “**Info.cern.ch**是世界上第一个网站及网站服务器。网站在一台位于CERN的NeXT计算机上运作。第一个网页地址是http://info.cern.ch/hypertext/WWW/TheProject.html 这个网站解释了万维网是什么，用户如何使用浏览器，如何创建网页服务器 

#### 2.HTTP 0.9 1991年

1991年 Tim根据之前的研究发表了一篇文章：HTTP基于TCP/IP实现，只有GET请求，响应返回的只有HTML文本，每个请求都是短链接。

#### 3.HTTP 1.0 1996年

拥有了更多功能，POST，HEAD请求，状态码，缓存，重定向，权限等

#### 4.HTTP 1.1 1997年

PUT，DELETE，OPTIONS等等 ，持久链接，管道机制，分块传输。

该版本也是目前最常用的HTTP协议版本。

#### 5.HTTP 2.0 2015年

对HTTP的一些改进和扩展。提高传输性能。普及率不高。

#### 6.HTTP 3.0 

QUIC（Quick UDP Internet Connections)协议 ,最早由谷歌提出,基于UDP的实现，改进UDP使其变得更加可靠，使效率更高。还未成为标准。

![image-20201122132124294](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122132124294.png)

2020.11.22 15：57

2020.11.22 21：07

### 2.透过TCP/IP看HTTP

![image-20201122210935055](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122210935055.png)

![image-20201122211039546](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211039546.png)

![image-20201122211110302](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211110302.png)

![image-20201122211132835](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211132835.png)

![image-20201122211203193](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211203193.png)

![image-20201122211227097](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211227097.png)

![image-20201122211247380](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211247380.png)

![image-20201122211335426](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211335426.png)

![image-20201122211442106](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211442106.png)

![image-20201122211956295](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201122211956295.png)

### 3.请求报文分析：

![image-20201124194835480](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124194835480.png)

![image-20201124195103450](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195103450.png)

![image-20201124195151936](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195151936.png)

![image-20201124195224492](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195224492.png)

![image-20201124195305066](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195305066.png)

![image-20201124195321970](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195321970.png)

![image-20201124195342541](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195342541.png)

![image-20201124195548357](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124195548357.png)

### 4.状态码：

![image-20201124202150857](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124202150857.png)

![image-20201124202314186](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124202314186.png)

![image-20201124202518875](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124202518875.png)

![image-20201124202700386](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201124202700386.png)