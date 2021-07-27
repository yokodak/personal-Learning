# 数据结构与算法学习笔记：

视频：JavaScript 数据结构与算法 精选班

链接： https://www.bilibili.com/video/BV1bT4y1j7BX?t=2 （失效）

链接2： https://www.bilibili.com/video/BV1x7411L7Q7?p=92 

创建日期：2020.10.10 13：00

Day 01  2020.10.10 13：00 开始

## 1.什么是数据结构：

数据结构就是在计算机中，组织和存储数据的方式。

![image-20201010130423606](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010130423606.png)

常见的数据结构：

![image-20201010140122432](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010140122432.png)

![image-20201010140310091](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010140310091.png)

## 2.什么是算法（Algorithm）

![image-20201010140523329](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010140523329.png)

## 3.栈结构：

![image-20201010142347457](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010142347457.png)

栈结构只允许在一端进行插入和删除 操作：最后插入的最先出栈

last In First Out

![image-20201010142709773](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010142709773.png)

![image-20201010142821365](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010142821365.png)

函数调用栈：

![image-20201010143150842](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010143150842.png)

### 栈结构面试题：答案c

注意，并不是一次性将这六个元素全部压入，而是可以压栈再出栈，出栈又压栈的。

![image-20201010143838675](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010143838675.png)

![image-20201010144003219](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010144003219.png)

### 栈结构的实现（封装）

![image-20201010144058634](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010144058634.png)

![image-20201010144415764](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010144415764.png)

基于数组实现栈结构：

![image-20201010145629452](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010145629452.png)

![image-20201010145437683](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010145437683.png)

使用栈：

![image-20201010145657637](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010145657637.png)

### 栈的应用-10进制转2进制：

**question：什么时候用this，什么时候不用this还是没搞懂。**

![image-20201010152948832](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010152948832.png)

![image-20201010150308684](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010150308684.png)

![image-20201010151059837](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010151059837.png)

## 4.队列结构：Queue：

**先进先出 First In First Out**

只允许在表的前端（front)删除，在表的后端(rear)进行插入（不能插队）

![image-20201010151320709](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010151320709.png)

![image-20201010151445518](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010151445518.png)

队列的应用：

![image-20201010151851401](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010151851401.png)

### 队列的实现：

基于数组的实现：

封装队列：

![image-20201010152125646](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010152125646.png)

![image-20201010153442623](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010153442623.png)

![image-20201010153957566](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010153957566.png)

![image-20201010154020069](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010154020069.png)

使用队列：

![image-20201010154132239](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010154132239.png)

### 队列面试题-击鼓传花：

（丢手绢）

![image-20201010154241897](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010154241897.png)

![image-20201010154420028](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010154420028.png)

算法思路：

将所有人放入队列，从队列的第一个人开始数数，未数到指定数字的人移动到队列末尾，数到指定数字的人从队列中删除，然后下一次数数开始，直到队列只剩一个人，游戏结束，那个人获胜。

![image-20201010154933174](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010154933174.png)

具体代码：

![image-20201010160932081](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010160932081.png)

![image-20201010161851882](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010161851882.png)

结果输出：Lilei

### 优先级队列：

（生活中类似会员可以优先办理业务等，医院急诊科等）

![image-20201010162016628](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010162016628.png)

![image-20201010162034547](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010162034547.png)

生活中的优先级队列：

![image-20201010162105787](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010162105787.png)

计算机中可以优先处理一些比较紧急的线程。 

![image-20201010162245984](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010162245984.png)

### 优先级队列的封装：

Priority Queue

每次调用enqueue方法都是在执行创建一个QueueElement的实例的函数

![image-20201010163332368](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010163332368.png)

**实现插入方法：**

splice方法插入数据：

![image-20201010165246688](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010165246688.png)

下面插入方法解析：假设现在队列里有两个优先级分别为1，和3的两个对象，现在要插入优先级为2的对象，判断到第二次时，i = 1,发现第二个元素的优先级（3）比当前元素（2）的优先级大，则在他前面也就是队列的第一个元素的后面插入对象，所以是splice（1，0，新对象）

![image-20201010165102092](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010165102092.png)

**实现其他方法**：

![image-20201010165746738](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010165746738.png)

使用优先级队列：测试：

![image-20201010165843804](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010165843804.png)

![image-20201010165907945](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010165907945.png)

**17：00**  pause

**19：00**  start



## 5.链表结构：

数组的缺点：

![image-20201010190438503](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010190438503.png)

链表的优势：

![image-20201010190715735](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010190715735.png)

链表的缺点：访问任何一个元素都要从头开始访问，线性查找。

![image-20201010190748699](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010190748699.png)

链表结构：

![image-20201010190918116](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010190918116.png)

![image-20201010191008615](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010191008615.png)

### 封装链表：

![image-20201010193620369](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010193620369.png)

![image-20201010193930767](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010193930767.png)

### 链表方法的实现：

- **append方法：**追加一个节点：

  找最后一个节点的过程：比如现在单链表内有2个节点（头和另外两个节点）此时length = 2 ,说明要追加的该节点不是第一个节点，则创建一个变量current来保存头节点，

  进入第一次循环，此时current = head ，所以current.next指向第一个节点，该节点不为空，所以进入while循环，更新current，令其等于第一个节点。

  进入第二次循环，此时current是第一个节点，current.next指向第二个节点，不为空，所以进入while循环更新current的值，

  进入第三次循环，此时current为第二个节点，也就是该链表内的最后一个节点，current.next指向null，所以不会进入while循环。

  跳出while循环后，将现在的current.next也就是第二个节点的next指向我们新追加的节点，完成添加节点操作。

  然后令链表的长度加1.

![image-20201010195303114](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010195303114.png)

- **toString**方法实现：

![image-20201010200745861](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010200745861.png)

测试append方法：

![image-20201010200809616](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010200809616.png)

- **insert**方法实现：

  需要分两种情况讨论：

  如果插入的位置是第1个也就是位置为0处，则先获取到head的值，也就是head指向的节点的地址，将该地址赋值给新节点的next，使其指向head一开始指向的节点。

  然后在将head的值改为新节点的地址this.head = newload
  使head指向新节点，这样新节点就变成了第一个节点，其next指向原来的第一个节点。

![image-20201010204053025](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010204053025.png)

第二种情况：不是第一个位置，假设position是1，也就是插入第一个节点后时：

先创建3个变量，index用来控制循环，current默认保存的是头节点指向的节点也就是第一个节点，previous用来表示之前的接节点.

第一次循环，index = 0 ,index++等于0，0<1，所以进入循环，previous = current,也就是说，此时的previous是第一个节点节点，然后更新current的值，使其成为第二节点

然后进行第二次循环，此时index = 1 ,index++等于1，不会再循环了，所以跳出循环。将新节点的next指向current也就是原来的第二个节点，将previous，也就是现在的第一个节点的next指向新节点，新节点就变成了现在的第二个节点，也就是链表位置1处。完成插入操作。然后令链表长度加1

**question** 

一个值怎么能成为一个节点呢？current此时应该是保存了第一个节点的地址。通过它就可以调用第一个节点

为什么current=head，而current的next是第二个节点？按道理来说，这样不是相当于head.next = 应该是第一个节点才对啊

比如head此时指向的是第一个节点，第一个节点的内存地址是0x123,

则head = 0x123,现在令current = head = 0x123,就可以通过current调用第一个节点，也就是说head和current都是第一个节点！

current = head 其实就是 current = head.next?不是

head其实就是一个指针，它指向谁，它就是谁!!就像第一个节点的next指向第二个节点，那它就是第二个节点，所以才可以把它赋值给current

head.next是第二个节点

- **get**方法实现：

![image-20201010213916401](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010213916401.png)

测试这两个方法：

![image-20201010213934490](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010213934490.png)

- **indexOf方法实现：**

![image-20201010222143654](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010222143654.png)

![image-20201010222638361](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010222638361.png)

测试：

![image-20201010222718423](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010222718423.png)



- **update**方法实现：

![image-20201010222804413](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010222804413.png)

![image-20201010223005428](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010223005428.png)

测试：

![image-20201010223035392](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010223035392.png)

- **remove**方法实现：

![image-20201010223116274](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010223116274.png)

移除特定项：（根据位置）

![image-20201010225210917](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010225210917.png)

测试：

![image-20201010225229715](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010225229715.png)

根据数据删除某个节点：

先获取数据（调用indexOf)所在的位置，根据位置删除节点(调用removeAt)即可：

![image-20201010230341750](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010230341750.png)

测试：

![image-20201010230258028](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010230258028.png)

- isEmpty和返回长度方法：

![image-20201010230524414](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010230524414.png)

![image-20201010230602872](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201010230602872.png)



Day 01 结束 2020.10.10 23：00 进度：32P结束

==Day 02==  2020.10.11 12：50 开始

### 双向链表：

单向链表的缺点：到达下一个节点简单，回到前一个节点很难

![image-20201011125317223](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011125317223.png)

![image-20201011125547352](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011125547352.png)

双向链表：一个节点既有向前的引用，也有一个向后连接的引用。

![image-20201011125630456](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011125630456.png)

双向链表缺点：

![image-20201011125807303](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011125807303.png)

![image-20201011130011000](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011130011000.png)

### 双向链表封装：

![image-20201011130552821](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011130552821.png)

### 双向链表的常见操作（方法）封装：

![image-20201011130713047](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011130713047.png)

- append方法实现：

![image-20201011132024813](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011132024813.png)

- 正反遍历双向链表实现：

  -  正向遍历双向链表：

    依次向后遍历（令current=head)，获取每一个节点，将其转换为字符串，直到current.next为空，也就tail指向null时，停止遍历，返回结果（一个字符串）

![image-20201011132537553](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011132537553.png)

- 反方向遍历双向链表：

  依次向前遍历（令current = tail )，获取每一个节点，将其数据转换为一个字符串，然后令current = current.prev 直到current为空，也就是第一个节点的prev为空时，停止遍历，返回字符串。

![image-20201011133105170](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011133105170.png)

question 为什么没有调用toString方法也能遍历双向链表为字符串，第一行alert(list)

answer:  toString方法（在使用alert时）会自动调用

 https://www.cnblogs.com/webflash/archive/2010/02/07/1665328.html 

toString方法的作用是不用多说的了，这个JavaScript内置方法还有一个特性是：在执行一些特殊方法的时候，比如alert或innerHTML等方法，它将由脚本解析器自动调用。这一特性显然有助于你偷懒，当然也有利于实现一些特定的功能。

测试： 

![image-20201011133004707](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011133004707.png)

- insert方法实现：

  先做越界判断：

![image-20201011142638466](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011142638466.png)

链表为空的话则添加新节点，不为空分3种情况:

位置为0处， 位置为链表长度处，其他情况。前两种见图上说明。

其他情况，比如现在链表长度为3，向position= 1处，也就是第二个节点处：

先令current = head，方便从头开始遍历找到要插入的位置，然后创建一个变量index来进行遍历，当遍历到当前位置的节点时（比如position = 1时），停止遍历，将新节点的next指向当前节点（newNode.next = current），然后将新节点的prev指向当前节点的的前一个节点（newNode.prev = current.prev),再把当前节点的前一个节点（current.prev)的next指向新节点（current.prev.next = newNode)，之后令新节点成为当前节点的前一个节点（current.prev = newNode)

![image-20201011140919738](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011140919738.png)

测试：

![image-20201011142025641](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011142025641.png)

- get方法实现：（根据特定位置获取元素）

  注意越界判断的时候和插入节点时不一样，当位置等于数组长度是是没有对应的节点的，也就获取不到元素。所以判断的时候要写>=

![image-20201011150452632](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011150452632.png)

测试：

![image-20201011142831948](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011142831948.png)

上面的方法默认是从前往后（current = this .head）遍历，但是如果我们要获取的节点的位置比较靠后，却还是要从头开始遍历，就会使性能变差。

因此我们可以根据要查找的位置和链表的长度进行比较，我们这里只分两种情况：

当位置小于链表长度的一半，说明要获取的元素在链表前半部分，这样我们就从头遍历；

当位置大于链表长度的一半，说明要获取的元素在链表后半部分，这样我们就从尾遍历；

（current = this.tail ，index = this.length -1 , while( index -- > position)

{

​	current = current.prev

}）

这样的话可以减少遍历，提高性能。

![image-20201011143248806](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011143248806.png)

- indexOf方法实现：

  因为我们也不知道传入的数据在链表的那个位置，所以无法决定从前还是从后遍历双向链表，这里我们任意选择一种遍历，下面代码是从前（头）开始遍历

![image-20201011144844579](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011144844579.png)

测试：

![image-20201011145016739](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011145016739.png)

- update方法：

  和get方法一样，我们也可以根据要查找的位置和链表的长度进行比较

  当位置小于链表长度的一半，说明要更新的元素在链表前半部分，这样我们就从头遍历；

  当位置大于链表长度的一半，说明要更新的元素在链表后半部分，这样我们就从尾遍历；

![image-20201011150331413](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011150331413.png)

![image-20201011145827377](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011145827377.png)

- removeAt方法：根据位置信息删除节点：

  一旦一个节点没有任何一个指针指向它，js的垃圾回收机制会自动将它回收

  实现思路和insert方法类似：

  如果链表不止一个节点则分3种情况：前面两种见图

  第三种情况：删除的是链表中间的节点:

  先根据index和position的关系遍历找到要删除的节点，跳出遍历后，让找到的节点的前一个节点的next指向当前节点的next（比如删除第三个节点，则将第二个节点的next指向第4个节点），然后将要删除节点的下一个节点的prev指向要删除节点的前一个节点（比如删除第三个节点，则将第4个节点的prev指向第2个节点）

  这样，该节点不再被任何元素所引用，会被自动回收。

![image-20201011151521329](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011151521329.png)

完善：

![image-20201011152449807](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011152449807.png)

测试：

![image-20201011152536987](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011152536987.png)

- remove方法的实现：

结合两个方法：首先根据传入的元素获取到该元素所在节点的

![image-20201011152946202](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011152946202.png)下标值（indexOf）然后根据下标值删除节点即可（removeAt)

测试：

![image-20201011152747114](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011152747114.png)

- 其他方法：isEmpty和size，获取链表的第一个元素，获取链表的最后一个元素

![image-20201011153022234](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153022234.png)

![image-20201011153047577](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153047577.png)

![image-20201011153131594](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153131594.png)

测试：

![image-20201011153202081](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153202081.png)

## 6.集合 Set

集合中的元素不允许重复，其中的元素是没有顺序的。

![image-20201011153415858](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153415858.png)

![image-20201011153456650](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153456650.png)

![image-20201011153543998](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153543998.png)

### 集合的封装：

ES6中Set类已经可以直接使用，但是我们还是自己来实现一下： 

封装集合类：使用对象来进行封装，因为对象的keys就是一个集合（属性的键名不允许重复）我们只需要将集合内的元素存储到对象的keys里即可。

![image-20201011153835064](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011153835064.png)

### 集合方法的实现：

![image-20201011154034321](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011154034321.png)

- add和has方法：

  添加和判断元素是否存在

![image-20201011154534733](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011154534733.png)

- remove，clear，size，values方法：

   `**Object.keys()**` 方法会返回一个数组。 

![image-20201011154937317](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011154937317.png)

测试集合类：

![image-20201011155638861](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011155638861.png)

### 集合间的操作：

![image-20201011155949558](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011155949558.png)

- **求并集**：

  求两个集合的并集：

![image-20201011161031325](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011161031325.png)

测试：

![image-20201011161130411](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011161130411.png)

- **求交集：**

  遍历集合A中的元素，如果存在于B中则加入差集

![image-20201011161634741](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011161634741.png)

测试：

![image-20201011161728307](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011161728307.png)

- 求差集：

  遍历集合A中的元素，如果不存在于B中则加入差集

![image-20201011161933942](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011161933942.png)

测试：

![image-20201011162105759](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011162105759.png)

- 求子集操作：

  遍历集合A中的元素，如果A有元素不存在于B中，则A不是B的子集，返回false,遍历完依然没有发现,则A是B的子集,返回true。

![image-20201011162325280](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011162325280.png)

测试：

![image-20201011162535127](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011162535127.png)

## 7.字典：（map）

question : JavaScript中字典和对象似乎没什么区别?

有，因为js中对象的属性名只能是字符串，但是有时候我们也需要使用数字或者其他数据类型来作为属性名，字典Ma解决了该问题

一对多，将多个元素封装为一个对象，就实现了一一对应。

![image-20201011162824956](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011162824956.png)

![image-20201011162911996](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011162911996.png)

和数组对比：

![image-20201011163228885](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011163228885.png)

和对象对比：

![image-20201011163205093](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011163205093.png)

字典的封装：

![image-20201014130133201](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014130133201.png)

字典的使用：

![image-20201011163457436](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011163457436.png)



**16:35**   pause

**19：30** start

## 8.哈希表

优势和不足：

![image-20201011194022594](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011194022594.png)

那么, 哈希表到底是什么呢? 

- 似乎还是没有说它到底是什么.
- 这也是哈希表不好理解的地方, 不像数组和链表, 甚至是树一样直接画出你就知道它的结构, 甚至是原理了.
- 它的结构就是数组, 但是它==神奇的地方在于对下标值的一种变换===, 这种变换我们可以称之为哈希函数, 通过哈希函数可以获取到HashCode.
- 不着急, 我们慢慢来认识它到底是什么.

案例一：用哈希表保存员工信息

- 通过张三这个名字, 我就能获取到它的索引值, 而再通过索引值我就能获取到张三的信息呢?
- 这样的方案已经存在了, 就是使用哈希函数, ==让某个key的信息和索引值对应起来==.

### 哈希概念引入

将字符串转换为下标值

![image-20201011195715749](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011195715749.png)

第一步：将字符转换为数字

解决方案：编码,ASCII码，UTF-等等，我们也可以自己设计一套编码系统

![image-20201011200955772](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011200955772.png)

第二步，一个字符串转成一个数值：

解决方案1：太少）字符编码相加得到的数字作为对应的数值，但是会有重复，所以不行

解决方案2：太多）幂的连乘，得到的结果太大，创建的数组空间太大，很多空间未被使用，造成浪费

![image-20201011201216750](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011201216750.png)

![image-20201011201510538](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011201510538.png)

![image-20201011201545624](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011201545624.png)

**最终方案：**优化方案2 ：

![image-20201011201630603](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011201630603.png)

如何压缩：

![image-20201011201831398](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011201831398.png)

![image-20201011201900543](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011201900543.png)

### 哈希化，哈希函数，哈希表：

哈希化：将大数字转换为数组范围内下标的过程

哈希函数:在哈希函数内编写将单词转换为大数值，大数值进行哈希化的代码

哈希表：将哈希函数获得的结果储存到一个数组，对其结构进行封装后称之为哈希表。

![image-20201011202036444](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011202036444.png)

### 哈希冲突：

哈希函数处理后得到的下标值一样

![image-20201011202744294](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011202744294.png)

![image-20201011202839784](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011202839784.png)

### 解决冲突

- 链地址法：（拉链法）

  数组的每一个元素是一个数组或者链表，其中再存放要查找的元素。

![image-20201011203530964](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011203530964.png)

![image-20201011203654369](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011203654369.png)

选择数组还是链表？效率差不多

根据实际需求来选择，如果需要经常进行比较新的数据（现实中，放在数组或者链表的最前面）插入最前端和存取的话，链表比较合适。但是也有其他情况数组比较合适，要进行适当分析后再进行选择。

![image-20201011203734750](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011203734750.png)

- 开放地址法：

  寻找空白的单元格来添加重复的数据。

![image-20201011204246514](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011204246514.png)

![image-20201011204424988](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011204424988.png)

根据探索空白位置方法的区别，又分为：线性探测，二次探测，再哈希法

![image-20201011204536717](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011204536717.png)

- 线性探测:

  一个个位置查找空白的位置，只要有空位就插入

![image-20201011204627657](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011204627657.png)

![image-20201011204813896](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011204813896.png)

查询插入的元素：一个个查找，查找到元素或者查找到**空位**就停止

![image-20201011205040432](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011205040432.png)

删除插入的元素：将该位置的数据置为-1，查找到该位置是会继续查找，但是插入时，这个位置可以放置数据。

![image-20201011205234844](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011205234844.png)

问题：**聚集**：当出现连续的填充单元时，我们需要探索多次才能插入数据，该问题会影响性能。

![image-20201011205604786](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011205604786.png)

- 二次探测：

  每次探测都一次性探测比较长的距离，比如第一次探测1个位置，第二次探测4个位置，第3次探测9个位置，每次探测的距离是当前探测次数的2次方，这样的话就能减小聚集带来的影响。

![image-20201011205731837](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011205731837.png)

问题：当连续插入的下标值是一样的时候，比如都是2，那么第一次探测（32）是2+1，第二次是2+4，第三次是2+9 。。。直到插入数据。

然后我们又插入一个数据（112），他的下标值也是2，那它也要探测之前32已经探测过的位置，如果要很多次探测才找到空位的话，那二次探测也带来了步长不一的一种聚集。还是会影响效率

但是出现该种聚集的可能性较小。

![image-20201011205805235](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011205805235.png)

- 再哈希法：

  不同的关键字使用不同的步长，再做一次哈希化，将这次哈希化的结果作为步长

![image-20201011210923624](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011210923624.png)

第二次哈希限制：不能和第一个哈希函数相同，不能输出为0

该函数已经被设计好了：

步数 = 一个常量（是质数）-（关键字的哈希结果%该常量）

该常量要小于数组的容量

例如：stepSize1 = 5 - （32 % 5 ） =5 -3 =2 

stepSize2 = 2 -(32 % 2) = 2 - 0 = 2

stepSize3 = 7-(32 % 7 ) = 7 -4 = 3

....

question : 每次常量不同么，常量怎么指定的？

![image-20201012162841236](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012162841236.png)

### 哈希的效率：

产生冲突后选择何种解决方案效率更高?

![image-20201011212349309](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011212349309.png)

装填因子：（load Factor）= 总数据项/当前哈希表的长度。

装填因子越小，效率越高。

在开放地址法中，装填因子的最大值是1,也就是没有空白单元放入的情况（哈希表被数据项填满）。

而在链地址法中，装填因子可以大于1，因为数据项（链条长度不止为1）可能会大于哈希表长度。

![image-20201011212503451](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011212503451.png)

![image-20201011213101689](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011213101689.png)

**开放地址法：**

线性探索的性能（效率）

![image-20201011213821407](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011213821407.png)

![image-20201011213904879](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011213904879.png)

**链地址法性能（效率）**

![image-20201011214315038](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011214315038.png)

![image-20201011214031238](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011214031238.png)

![image-20201011214418235](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011214418235.png)

链地址法效率更高：

对比两张图发现链地址法不会因为装填因子的增大(添加了新元素）而使探测长度急剧增大而导致性能下降。

### 什么才是优秀的哈希函数：

![image-20201011215121297](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011215121297.png)

- 快速的计算：

  哈希：将字符串转换为大数值：

  **幂的连乘**：计算效率：

![image-20201011215415341](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011215415341.png)

多项式优化：

**秦九韶算法：** (霍纳法则)

一般地，一元n次[多项式](https://baike.baidu.com/item/多项式)的求值需要经过(n+1)*n/2次[乘法](https://baike.baidu.com/item/乘法)和n次[加法](https://baike.baidu.com/item/加法)，而秦九韶算法只需要n次乘法和n次加法。在人工计算时，一次大大简化了运算过程。

把一个n次多项式

![img](https://bkimg.cdn.bcebos.com/formula/e9c952034174fd5a35a4fbf9ab734bd6.svg)

改写成如下形式：

![img](https://bkimg.cdn.bcebos.com/formula/ec1e6d168b1abb8b7cdef8cb52a49495.svg)

![img](https://bkimg.cdn.bcebos.com/formula/c2f6fb3d09607f7031d252b85128a7fa.svg)

![img](https://bkimg.cdn.bcebos.com/formula/0012cc323cac657bda7badf161155175.svg)

![img](https://bkimg.cdn.bcebos.com/formula/2999cb002e842f805ed7f1c0e353d9ea.svg)

![img](https://bkimg.cdn.bcebos.com/formula/b0b00385d65a75d4c4c0a88fcb9cec75.svg)

![img](https://bkimg.cdn.bcebos.com/formula/2f0354b5c8fff711611f251a4c5687c2.svg)

```js
var ans = 0 ;//多项式初始为0
function getAns(str, x)//求出该多项式的结果
//以字符串形式传入每个项的系数，从最高项开始,传入x作为幂的底数的值
{
    for(var i =0 ;i < str.length ; i++)
        {
            ans = ans * x + str[i]
        }
    return ans
}
```



```c
#include <iostream>
#include <cstdio>
#include <cstdlib>
#include <cmath>
using namespace std;
int main() {
    int n;
    cout << "请输入多项式的次数 ：";
    cin >> n;
    double *a = new double[n+1];//n次多项式申请n+1大小的数组
    cout << "请输入多项式的系数（最高次项开始）:" << endl;
    for(int i = n; i >= 0; i --)
        cin >> a[i];//读入各项系数
    double x0,ans=a[n];
    cout << "请输入 X0 " << endl;
    cin >> x0;
    for(int i = n-1;i >= 0;i --)
        ans = ans*x0 + a[i];////////!!最高次项开始，往外展开
    cout << "多项式在X0出的函数值为：" << ans << endl;
    delete []a;//释放动态内存
    return 0;
}
```

![image-20201011220404623](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011220404623.png)

- 均匀的分布：

使用质数：

![image-20201011223239817](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201011223239817.png)

![image-20201012162241115](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012162241115.png)

Day 02 结束 2020.10.11 22：40 进度：65P结束

Day 03 2020.10.12 09：45 开始

### 哈希函数的实现：

取余为什么重复概率小：如果不取余，直接使用hashCode作为下标值存储数据的话，需要申请一个比较大的内存空间，并且该数组存在大量未被使用的空间会造成空间浪费，所以为了压缩hashCdeode使其在数组范围内，我们使用取余操作。

而如果不使用幂的连乘作为hashCode的话，使用其他方案：比如各字符的编码相加：如abc假设编码分别123，hashCode = 6 ，直接将其作为下标值。现在还要存储一个字符串：cba ，相加得到的结果也是6，bac也是 ，acb也是。。。而只是换了一下字母顺序就造成大量的重复，这样后面加入的数据将没有空间存储。

而一个很大的数取余之后，得到的余数，相同的概率则比使用上面的方案得到的hashCode重复概率小，比如cba和abc，进行幂的连乘后再取余的结果不重复。

![image-20201012102311815](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012102311815.png)

将该方法放到hashTable类

![image-20201012124844521](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012124844521.png)

## 9.哈希表的封装：

哈希表是可以无限延申的

![image-20201012103352572](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012103352572.png)

结构分析：hash表是一个数组，每个下标值存放的是一个数组用来存储数据，

在该存放数据的数组内的每一个元素是一个数组来保存数据，数据的存放形式是一个数组，这样我们能根据key查找到元素。

![image-20201012104344819](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012104344819.png)

![image-20201012141857723](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012141857723.png)

![image-20201012104404883](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012104404883.png)

![image-20201012103730424](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012103730424.png)

**10：45**  pause

**13：00**  start



### 哈希表的方法（操作）的封装：

- 插入和修改的操作：

![image-20201012125545755](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012125545755.png)

![image-20201012141857723](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012141857723.png)

**storage的最大长度是7。是我们在创建hashTable类的时候在类的属性中指定的，用来做为哈希函数取余的底数，所以取余的结果，也就key的index不会大于7，因此storage的最大长度也就是7** 

在js中数组的长度是不固定的，所以一开始我们封装哈希表时，虽然storage是一个空数组，但是我们要存储index为7 的数据时，仍然可以直接让storage[7] = bucket

![image-20201012142952410](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012142952410.png)

- 获取操作封装：

![image-20201012132620382](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012132620382.png)

桶存在，说明要么是该key对应的数据之前已经被插入，（如员工张三的信息已经被插入桶中，或者有和该key对应的索引值相同的元素在之前被（比如假设李四对应的index也是和张三一样的是3，那么李四和张三会被放在同一个桶中）插入了桶中，所以才需要根据key值遍历进行线性查找）

![image-20201012134718244](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012134718244.png)

- 删除操作封装：

![image-20201012135320069](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012135320069.png)

![image-20201012140239062](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012140239062.png)

- 其他方法封装：

![image-20201012140732690](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012140732690.png)

测试哈希表：

![image-20201012140923376](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012140923376.png)

### 哈希表扩容：

**storage的最大长度是7（0-6）。**

是我们在创建hashTable类的时候在类的属性中指定的，用来做为哈希函数取余的底数，所以取余的结果，也就key的index不会大于7，因此storage的最大长度也就是7 。

而使用链地址法创建的哈希表是可以无限的插入数据的，随着数据项的增多，桶会越来越长。随着桶的增长，线性查找数据的时间就会越来越长，造成效率的低下。

而我们要扩容的就是storage的最大长度，让索引不止在0-6之间，从而减小bucket的长度

![image-20201012141113372](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012141113372.png)

![，](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012144915604.png)

扩容后，哈希函数计算出来的索引值也和之前不再相同，再执行查找删除等操作是无法查找到数据的的，所以所有的数据项，在进行扩容的同时也要重新进行插入（调用哈希函数，插入到新计算出来的索引处）

扩容前：

![image-20201012144308342](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012144308342.png)

扩容后：

![image-20201012144703561](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012144703561.png)

### 扩容（及缩小容量）的实现：

什么时候需要扩容？

当装载因子大于0.75时：总数据项/哈希表长度（limit）>0.75 时

![image-20201012150035139](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012150035139.png)

有时候也需要缩小容量：在删除后，比如1000个数据被删除到只剩6个，这样仍然用1000的空间去存储6个数据就比较浪费空间，所以需要缩小容量。但是缩小也要有个限度，我们设置storage最小为7。

缩小到其原容量的1/2，向下取整。

![image-20201012150557229](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012150557229.png)

扩容方法实现：resize

put方法内会调用哈希函数，在调用时会把新的limit传入，作为取余的size，从而实现索引值index的改变。（比如以前是0-6之间的5）现在重新计算后变成（0-13，扩大了两倍）的12 （只是举例，不是真实的计算结果），然后将桶里取出的数据放到该索引对应的桶里，这样原本最大长度为7的storage就扩容为了14.

当我们不断在表中添加数据时，随着数据的增多也要跟着一起扩容，随着数据减小也要缩小容量，所以在插入和删除数据的方法中，每次插入和删除数据后都需要进行扩容（或者缩小容量）的判断。

![image-20201012151601089](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012151601089.png)

### 质数判断算法：

更多性能改进见：

 https://blog.csdn.net/qq_41939020/article/details/99167166 

普通算法：（效率低）

![image-20201012160125350](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012160125350.png)

改进算法：

![image-20201012160455582](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012160455582.png)

~~还有更提高性能的方法：只需要判断能否被2-sqrt(该数字)之间的质数整除即可，能就不是质数。~~

### 实现容量恒为质数：

在优秀的哈希函数里我们提到要实现均匀的分布，最好是把使用到常量的地方使用质数：

![image-20201012161250491](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012161250491.png)

判断质数的方法封装：

![image-20201012161552879](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012161552879.png)

获取质数的方法封装：

![image-20201012161921301](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012161921301.png)

实现容量恒为质数:

![image-20201012161958506](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012161958506.png)

![image-20201012161742262](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012161742262.png)

**16：35** pause

**19：35** start

## 10.树结构：

![image-20201012194001844](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012194001844.png)

回顾之前学习的数据结构的优缺点：

数组：

![image-20201012194207779](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012194207779.png)

链表：

![image-20201012200030125](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012200030125.png)

哈希表：

![image-20201012200139232](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012200139232.png)

树结构的优点：

![image-20201012200223045](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012200223045.png)

### 树结构的术语：

![image-20201012200434102](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012200434102.png)

节点的度:节点的子树个数（子节点的个数），树的度：该数最多有几个子节点

![image-20201012200503211](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012200503211.png)

路径包含起点和终点，路径长度是路径包含的边的数目

![image-20201012201148379](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012201148379.png)

### 树的表示：

普通表示方式：

![image-20201012201316654](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012201316654.png)

优化后：

儿子-兄弟表示法：

![image-20201012201435620](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012201435620.png)

![image-20201012201639386](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012201639386.png)

旋转45度：

![image-20201012201812209](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012201812209.png)

![image-20201012201826420](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012201826420.png)

## 11.二叉树：

每个节点最多只能有两个节点

![image-20201012202033015](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012202033015.png)

二叉树形态：

![image-20201012202151815](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012202151815.png)

1.二叉树的特性：第i层最大节点数是2的i-1次方，i >= 1;（2的（5-1）次方）

2.深度为k的二叉数最多节点数为2的k次方减1个，k >= 1. （32-1）

3.非空二叉树，叶节点的个数比有两个子节点的节点数多1：n0= n2  +1 

![image-20201012202312700](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012202312700.png)

![image-20201012203625462](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012203625462.png)

满二叉树：

![image-20201012204019462](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012204019462.png)

完全二叉树：满二叉树是特殊的完全二叉树

![image-20201012203955136](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012203955136.png)

### 二叉树存储方式：

数组和链表：

数组方式：

完全二叉树：用数组从上到下，从左至右存储。

![image-20201012204500560](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012204500560.png)

非完全二叉树需要先转换为完全二叉树再使用数组存储：

![image-20201012204821261](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012204821261.png)

链表方式：比较常用：

非完全二叉树：

![image-20201012204952813](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012204952813.png)

### 二叉搜索树

（BST，Binary Search Tree）

也称为二叉排序树，二叉查找树；

特性见图：较小的值总是保存到左节点上，较大的值总是保存在右节点上，**且二叉搜索树没有键值相等的节点**

![image-20201012210248179](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012210248179.png)

![image-20201012205529977](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012205529977.png)

![image-20201012210028780](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012210028780.png)

二叉搜索树的优点：查找效率高

二叉搜索树就是二分查找思想的一种实现。

找10，从根节点开始找，二叉搜索树的根节点是9，10比9大，所以向二叉搜索树的右边查找，来到13，10比13 小，所以到13的左子树查找，来到11，10比11 小，所以到11的左子树查找，找到10，只查找了3次就找到10，相比于线性查找10次才找到10，效率高了很多。

![image-20201012210613537](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012210613537.png)

### 二叉搜索树的封装：

![image-20201012211607410](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012211607410.png)

![image-20201012211809426](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012211809426.png)

### 二叉搜索树的方法实现：

![image-20201012211934830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012211934830.png)

- insert（key） 插入方法：

实现思路见图：

![image-20201012215141753](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012215141753.png)

测试：

![image-20201012215318445](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012215318445.png)

![image-20201012215342285](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012215342285.png)

### 遍历二叉搜索树：

根据什么时候处理根节点来命名，先遍历根节点就是先序遍历

还有其他理解：先处理当前节点，再处理他的左右节点的叫先序遍历

![image-20201012215702804](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012215702804.png)

红色箭头方向为层序遍历：

![image-20201012215759975](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012215759975.png)

- 先序遍历：（POT)

previous Order Traversal

先访问左子树再访问右子树

![image-20201012215934609](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012215934609.png)

![image-20201012230650514](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012230650514.png)

![image-20201012221527305](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012221527305.png)

**question：**

==怎么回退的？一==旦左节点为空不就停止判断了么？为什么还会继续遍历右节点？ 处理到最后一个左节点时，跳出的判断不是整个大判断，而是它自己本身的一个小判断，当该判断不满足条件时，就会跳出来执行判断右节点的那条代码；

递归函数其实就是在函数内嵌套了一个自己，当他不满足自己的条件时，并不会把整个大判断终止，而是结束自己的那条代码，接着大判断内的其他代码照常执行，但是一旦递归没有结束，**就不会执行接下来的代码**。

![image-20201012222059066](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012222059066.png)

非递归方法：

```js
var preOrderTraversal = function (root) {//栈实现
  var res = [];//保存结果
  var stack = [];
  var node = root;
  while (node !== null || stack.length !== 0) {
    if (node !== null) {
      res.push(node.key);
      stack.push(node);
      node = node.left;
    } else {
      node = stack.pop();
      node = node.right;
    }
  }
  return res
};
console.log(preOrderTraversal(binaryTree.root)) // [19, 8, 5, 15, 12, 24, 45]
```

- 中序遍历：

![image-20201012224645406](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012224645406.png)

![image-20201012224831834](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012224831834.png)

非递归方法：

```js
var inorderTraversal = function (root) {
  let result = [];
  let stack = [];
  let node = root;
  while (node !== null || stack.length !== 0) {
    if (node !== null) {
      stack.push(node);
      node = node.left; // 遍历左，存入栈中
    } else {
      debugger;
      // node===null时说明左边没有了，那么栈顶就是最左边的（最小的）
      node = stack.pop();
      result.push(node.key);
      node = node.right; //看右边有没有
    }
  }
  console.log(result); // [5, 8, 12, 15, 19, 24, 45]

  return result;
};

inorderTraversal(binaryTree.root);
```

- 后序遍历：

![image-20201012225127678](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012225127678.png)

![image-20201012225236565](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012225236565.png)

测试：

![image-20201012225155395](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201012225155395.png)

Day 03 结束 2020.10.12 23：00 进度：91P结束

Day 04 2020.10.13 13:00 开始

### (续)二叉搜索树的方法实现：

- 搜索最大值和最小值：

  最大值：

![image-20201013131113172](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013131113172.png)

最小值：

![image-20201013131216331](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013131216331.png)

测试：

![image-20201013131126506](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013131126506.png)

- 搜索特定key：

  递归实现：

![image-20201013131429976](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013131429976.png)

循环实现：

![image-20201013131747943](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013131747943.png)

测试：

![image-20201013131808628](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013131808628.png)

### 二叉搜索树的删除：

先找到要删除的节点：

![image-20201013133209813](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013133209813.png)

然后分3种情况：

![image-20201013132214329](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013132214329.png)

- 删除叶子节点：

将叶子节点的父节点的左节点（右节点）删除即可。

![image-20201013132432460](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013132432460.png)

![image-20201013133625646](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013133625646.png)

- 删除只有一个子节点的节点：

![image-20201013133733443](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013133733443.png)

![image-20201013133903007](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013133903007.png)

![image-20201013152850200](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013152850200.png)

![image-20201013140006103](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013140006103.png)

- 有两个子节点的节点的删除：

![image-20201013140919739](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013140919739.png)

分3种情况讨论，由简入繁：

**删除9节点：**（是父节点的右节点）

也可以移动10.

![image-20201013143419145](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013143419145.png)

**删除7 节点：**（是父节点的子节点）

处理方式1：

![image-20201013143358232](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013143358232.png)

处理方式2：

![image-20201013143540109](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013143540109.png)

**删除15节点：**

处理方式1：

![image-20201013144305980](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013144305980.png)

处理方式2：

![image-20201013144127512](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013144127512.png)

删除规律：

经过以上几个删除操作：我们发现一个规律，用来替换当前要删除的节点的那个节点，它的key值和当前要删除节点（current节点）的key值相差最小!

可以比他大也可以比他小。

![image-20201013144810529](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013144810529.png)

![image-20201013144932700](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013144932700.png)

### 前驱和后继：

前驱就是该节点左子树的最大值，后继就是该节点右子树的最小值

后继的key大于当前节点的key，前驱的key小于当前节点的key

所有节点中，和当前节点的key相差最小的两个节点，称为当前节点的前驱和后继，key相差最小且小于当前节点的，称为当前节点的前驱，key相差最小且大于当前节点的，称为当前节点的后继：

![image-20201013145301667](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013145301667.png)

为了实现节点的删除功能，我们首先要找到当前节点的前驱或者后继：

![image-20201013145623051](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013145623051.png)

- 找后继的代码实现：

  注意，在这里处理了删除节点的一部分操作，当就后继节点不是删除节点的右节点的时候，把后继节点的右节点作为（赋值给）后继节点的父节点的左节点，然后将删除节点的右节点赋值给后继节点的右节点，也就是后继节点的右节点现在是删除节点的右节点（因为后继节点把要删除的节点替换了，所以这是理所当然的）

  // 找后继的方法，也就是找右子树里的最小值

![image-20201013145915631](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013145915631.png)

```javascript
// 找后继的方法，也就是找右子树里的最小值
BinarySerachTree.prototype.getSuccessor = function (delNode) {//传入需要寻找后继的节点
    // 1.使用变量保存临时的节点
    var successorParent = delNode//后继的父节点，默认是自己
    var successor = delNode//successor是接班人，后继的意思
    var current = delNode.right // 要从右子树开始找

    // 2.从当前节点的右子树开始寻找节点
    while (current != null) {
        successorParent = successor//==delnode，一步步将后继的往下延申直到找到后继
        successor = current//令后继等于当前查找到的节点
        current = current.left//从左子树开始找，因为要找右子树里的最小节点
    }

    // 3.如果是删除图中15和7的情况, 还需要如下代码
    //就是如果后继节点不是删除节点的右节点的时候
    if (successor != delNode.right) {
        successorParent.left = successor.right
        successor.right = delNode.right
    }
    
    return successor
}
```

![image-20201013154736398](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013154736398.png)

### (续)完成二叉搜索树的删除功能：

找到后继节点后:

![image-20201013153712389](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013153712389.png)

删除节点的一部分操作，当就后继节点不是删除节点的右节点的时候，把后继节点的右节点作为（赋值给）后继节点的父节点的左节点，然后将删除节点的右节点赋值给后继节点的右节点，也就是后继节点的右节点现在是删除节点的右节点（因为后继节点把要删除的节点替换了，所以这是理所当然的）

在获取后继节点的函数中处理完成了

question:

其实获取后继的方法里，不是应该只负责获取到后继就可以了么？将判断的内容交到删除的方法里不是分工更明确么？（是因为变量的获取问题还是？）

```javascript
// 5.删除有两个节点的节点
else {
    // 1.获取后继节点
    var successor = this.getSuccessor(current)
    
    // 2.判断是否是根节点
    if (current == this.root) {
        this.root = successor
        //如果是根节点，将后继变为根即可，root的左节点本来就有指向，当后继成为根后，它的左节点就是root的左节点，没有改变。
    } else if (isLeftChild) {//如果是父节点的左节点
        parent.left = successor//父节点的左节点替换为后继
    } else {
        parent.right = successor
    }
    
    // 3.将删除节点的左子树赋值给successor
    successor.left = current.left //删除节点的左子树成为后继的左子树
}
```

测试：

![image-20201013160858980](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013160858980.png)

### 二叉搜索树的缺陷：非平衡树

当插入连续的数据后，二叉树节点的分别变得非常不均匀，我们称之为非平衡树，这样的二叉树会使查找效率变低。

![image-20201013162310778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013162310778.png)

![image-20201013162620926](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013162620926.png)

![image-20201013162830935](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013162830935.png)

**16：30**   pause

**18：30**   start

## 12.红黑树：

### 红黑树特性

红黑树的特性：

![image-20201013184014028](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013184014028.png)

节点都有==颜色==，除了叶子节点外，每个节点都必须有两个子节点（完全二叉树）

叶子节点都是黑色的**空**节点。根节点是黑色节点。

**红色节点的两个子节点必须是黑色** 且从每个叶子节点到根的所有路径上不能有两个连续的红色节点（因为红节点的子节点必须是黑色）如下图，1，11，15，25 都不能是红色。

从任意一个节点开始到 **其 **叶子节点所经过的黑色节点数一样：

比如从8到其叶子节点的所有路径上经过的黑色节点数目都是2.

![image-20201013190806051](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013190806051.png)

以上约束：确保了红黑树的关键特性：

**从根到叶子的最长可能路径，不会超过最短可能路径的两倍长。**

如上图：根到绿色圈节点的路径是最短可能路径（之一）长度是3，最长可能路径（之一）黄色圈的长度是4，不会超过3的两倍

![image-20201013190504685](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013190504685.png)

### 红黑树的平衡

相对平衡

**为什么：**

因为只要一条路径上全是黑色节点，那该路径一定是最短路径，假设该路径上有4个黑色节点，而根据红黑树的特性可以得知：从根节点到其每一个叶子节点的路径所包含的黑色节点数相同，也就是说可能的最长路径也最多有4个黑色节点，如果还要更长，只能是该路径上存在红色节点，而红色节点必须是连续的，所以最多3个：（黑-==红==-黑-==红==-黑-==红==-黑）可知该最长路径的长度最大是7，7<4*2 

所以：

**从根到叶子的最长可能路径，不会超过最短可能路径的两倍长。**

![image-20201013193608803](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013193608803.png)

![image-20201013192353621](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013192353621.png)

**19：35** pause

**20：35** start

### 让红黑树保持平衡

让红黑树保持相对平衡的方法：

- 红黑树的变色：

![image-20201013204500213](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013204500213.png)

新插入的节点通常都是红色节点：这样能在保持红黑树平衡的同时**大部分情况下**不违反红黑树的规则。

![image-20201013205007124](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013205007124.png)

- 旋转：

![image-20201013205354979](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013205354979.png)

- **左旋转：**

![image-20201013211458062](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013211458062.png)

- **右旋转：**

![image-20201013211822825](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013211822825.png)

### 红黑树的方法实现：

- 插入：

![image-20201013212619057](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013212619057.png)

![image-20201013212705275](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013212705275.png)

分情况：

情况1：空树

向空树中插入节点：直接插入节点，使其成为根节点，将其变成黑色即可。

![image-20201013212959678](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013212959678.png)

情况2：父节点为黑

新节点的父节点p是黑色节点：直接插入即可

![image-20201013213343112](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013213343112.png)

![image-20201013213137716](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013213137716.png)

情况3：父和叔都黑

P和U都是红色节点：将祖父节点变为红色，父节点和叔节点都变成黑色，但是如果G节点的父节点以前就是红色节点，那进行变换后，又出现了红红相连的情况，这个时候我们用递归来解决，但是如果递归到根节点，而根节点不能为红色，则需要进行旋转，我们后面会再讨论。

![image-20201013214952182](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013214952182.png)

![image-20201013213818814](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013213818814.png)

![image-20201013213933670](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013213933670.png)

出现的问题：

![image-20201013215150830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013215150830.png)

情况4：父红，叔黑祖黑，且N是左儿子

![image-20201013215619551](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013215619551.png)

![ ](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013221219127.png)

![image-20201013215519399](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013215519399.png)

![image-20201013215559837](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013215559837.png)

情况5：父红，叔黑祖黑，且N是右儿子

对P左旋转，对G右旋转

![image-20201013230518720](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013230518720.png)

![image-20201013224504014](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013224504014.png)

![image-20201013224630882](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013224630882.png)

![image-20201013225023671](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013225023671.png)

### 红黑树插入案例练习：

![image-20201013231329427](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201013231329427.png)

Day 04 结束  2020.10.13 23：15 进度： 110P结束

==Day 05== 2020.10.14 09：30开始

插入7：

![image-20201014093716019](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014093716019.png)

插入6：

![image-20201014094210566](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014094210566.png)

插入5：

![image-20201014094357678](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014094357678.png)

插入4：

![image-20201014094614772](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014094614772.png)

**插入3：**

![image-20201014095127104](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014095127104.png)

插入2：情况4

![image-20201014095311219](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014095311219.png)

插入1：

![image-20201014095601454](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014095601454.png)

![image-20201014095829825](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014095829825.png)

## 13.图论：图结构：

### 什么是图结构：

由点（顶点）和边组成的图形，主要研究的是事物间的关系，顶点代表事物，边代表两个事物间的关系

![image-20201014100033985](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014100033985.png)

六度空间理论：

![image-20201014100428603](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014100428603.png)

图的现实案例：

比如人和人的关系网，地铁路线图：

![image-20201014100631776](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014100631776.png)

### 图结构的特点：

一组顶点（Vertex）

一组边（Edge),边可以是有向的也可以是无向的

无向边 A-----B  ,有向边： A ------> B

![image-20201014101442727](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014101442727.png)

欧拉七桥问题：

![image-20201014102118781](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014102118781.png)

![image-20201014102144863](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014102144863.png)

![image-20201014102256804](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014102256804.png)

![image-20201014102549936](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014102549936.png)

### 图的术语：

![image-20201014102936634](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014102936634.png)

![image-20201014102952559](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014102952559.png)

![image-20201014103010581](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014103010581.png)

![image-20201014103104955](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014103104955.png)

![image-20201014103220476](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014103220476.png)

如下图：绿色线路不包含重复的顶点，所以是一条简单路径

蓝色路线0-3-6-7-3-6-8-9，包含了重复的顶点所以不是简单路径

箭头所指路线，起点和终点都是0，称之为回路。

![image-20201014103411423](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014103411423.png)

![image-20201014103812844](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014103812844.png)

![image-20201014104012171](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014104012171.png)

### 图的表示：

![image-20201014104239003](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014104239003.png)

- 邻接矩阵：

![image-20201014104423937](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014104423937.png)

![image-20201014104553376](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014104553376.png)

二维数组：P[0]  [2] 为1表示A和C之间有连线，如果 P [2]  [0] 也为1 说明A和C之间是无向的。

如果想表示权重，将1换为其他数字表示顶点间路径的权重即可。

![image-20201014105218256](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014105218256.png)

![image-20201014105154074](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014105154074.png)

![image-20201014105258039](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014105258039.png)

邻接矩阵的问题：稀疏图：

![image-20201014105431627](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014105431627.png)



**11：00** pause

**12：50** start

- 邻接表：

计算出度比较简单，也就是指向其他顶点的数量，但是计算入度比较麻烦，（其他顶点指向自己的数量）比如想要找到A的入度，只能把整个表全部遍历一遍来查找指向A的顶点。或者构建一个逆邻接表

![image-20201014124856351](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014124856351.png)

![image-20201014125313778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014125313778.png)

![image-20201014124955336](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014124955336.png)

![image-20201014125037199](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014125037199.png)

缺陷：

![image-20201014125355600](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014125355600.png)

### 图结构的封装：

利用字典来保存边：实际上是数组在存储，字典中，key是顶点，value是保存顶点对应的边的一个数组

字典的封装：

![image-20201014130059723](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014130059723.png)

用一个数组来保存顶点，用一个字典来保存边：

![image-20201014130335778](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014130335778.png)

![image-20201014133930947](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014133930947.png)

![image-20201014133947988](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014133947988.png)

question：图结构是不是可以直接用一个字典来存储就好？

key对应顶点

value，一个数组，存储相连的边

### 图的方法实现：

- 添加顶点和边：

边是由两个顶点相连才形成一条边，我们将顶点单独存储在一个数组，而边则使用键值对的方式存储：比如  A：[B,C,D] 表明存在3条边分别是AB,AC,AD

![image-20201014140945939](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014140945939.png) 

测试：

![image-20201014134420962](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014134420962.png)

**14:15** pause

**16:00** start

- toString方法：

![image-20201014161132797](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014161132797.png)

![image-20201014161200148](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014161200148.png)

### 图的遍历：

![image-20201014161837880](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014161837880.png)

![image-20201014162635186](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014162635186.png)

初始化颜色：

Js中数组的下标值是可以为字符串的，因为js中的数组也是一个对象。

![image-20201014163322295](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014163322295.png)

- BFS：广度优搜索

  (Breadth-First-Search) 

![image-20201014164005065](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014164005065.png)

![image-20201014174946957](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014174946957.png)

**代码实现：**

传入一个初始化顶点，和处理顶点的函数

![image-20201014175220830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014175220830.png)

![image-20201014173839711](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014173839711.png)

![image-20201014174630122](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014174630122.png)

测试：

![image-20201014175220830](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014175220830.png)

![image-20201014175243717](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014175243717.png)

**18：00**  pause

**19：10**  start



- DFS：深度优搜索：

  (Depth-First-Search) 

![image-20201014191150681](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014191150681.png)

![image-20201014192015344](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014192015344.png)

![image-20201014191250416](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014191250416.png)

![image-20201014192220991](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014192220991.png)

测试：

![image-20201014192238549](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014192238549.png)

![image-20201014192057323](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014192057323.png)

## 14.排序算法：

### 大O表示法：

一种对算法效率的粗略度量。

当数据量发生变化时，算法的效率也会发生变化。

![image-20201014192921930](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014192921930.png)

### 认识排序：

![image-20201014202149367](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202149367.png)

![image-20201014202135454](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202135454.png)

### 列表类的封装：（方便测试）

将排序算法作为该类的方法添加到该类的原型，在测试时只需要调用相应的方法即可：

![image-20201014202308559](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202308559.png)

![image-20201014202238677](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202238677.png)

### 冒泡排序：

![image-20201014202500195](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202500195.png)

第一次冒泡排序：

![image-20201014202514608](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202514608.png)

- 代码实现：

  代码思路：

![image-20201014202633872](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202633872.png)

交换两个数据的位置的代码封装：

因为在排序算法中，我们会频繁地交换两个元素的位置，我们将交换位置的代码封装后，以后要交换位置时，不用重复写代码，直接调用该方法即可。

![image-20201014202942145](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014202942145.png)

冒泡排序代码：

![image-20201014204340095](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014204340095.png)

代码实现分析：

![image-20201014204040732](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014204040732.png)

验证：

![image-20201014203246858](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014203246858.png)

排序前：

![image-20201014203705081](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014203705081.png)

排序后：

![image-20201014203720891](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014203720891.png)

- 冒泡排序的效率：

比较次数：

![image-20201014204614393](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014204614393.png)

大O表示法：

![image-20201014204741333](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014204741333.png)

交换次数：平均大概每两次比较进行依一次交换：

![image-20201014204939227](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014204939227.png)

### 选择排序：

改进了冒泡排序

![image-20201014205158366](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014205158366.png)

- 代码实现：

![image-20201014211218910](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014211218910.png)

验证：

![image-20201014211240119](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014211240119.png)

- 选择排序的效率：

比较次数和冒泡排序一样，但是交换次数只有N-1次

![image-20201014212556583](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014212556583.png)

![image-20201014212515498](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014212515498.png)

### 插入排序：

![image-20201014212709741](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014212709741.png)

![image-20201014212756280](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014212756280.png)

![image-20201014220953980](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014220953980.png)

![image-20201014213240987](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014213240987.png)

- 代码实现：

  注意：关于i和temp的修改都是在while循环外的，每次while循环只是改变了j的值，依次将当前取出的值（array[i]也就是temp）和它前面的数据进行比较，只要前面的数大于它，那么它在数组内的位置就会被前面的数据所代替，然后在进行比较直到小于前面的数，或者比较到了第1个位置。

  上图76和10比较时，76>10，所以j不变，j= i ，所以76的位置不变（将自己赋值到自己的位置）

  而它前面的数每次会while循环都会进行更新，依次下标减一。

![image-20201014214305807](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014214305807.png)

![image-20201014221220618](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014221220618.png)

- 插入排序的效率：

  相对于选择排序**比较次数少了一半**，不需要交换数据，只需要给数组下标赋值即可。而且当数据有序时，不需要进入while循环，减少了循环的次数

![image-20201014221433080](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014221433080.png)

![image-20201014221645883](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014221645883.png)

![image-20201014221719521](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014221719521.png)

### 希尔排序：

![image-20201014223714823](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201014223714823.png)

Day 05 结束 2020.10.14   22：40    进度145P结束

Day 06 2020.10.15 09：50 开始

插入排序的问题：

![image-20201015095020156](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015095020156.png)

希尔排序的思路：分组，依次将分组的间隔减小直到1

![image-20201015095625040](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015095625040.png)

选择合适的增量（间隔）：

![image-20201015100201834](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015100201834.png)

- 代码实现：

  ~~注：在里层while循环里只要j>0即可，不需要j>gap -1~~

![image-20201015104247229](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015104247229.png)

解析：

![image-20201015104435530](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015104435530.png)

验证：

![image-20201015101320598](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015101320598.png)

- 希尔排序的效率：

![image-20201015104532358](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015104532358.png)

### 快速排序：

![image-20201015104832668](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015104832668.png)

![image-20201015104914684](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015104914684.png)

快速排序的思想：分而治之，一次性将数据插入到正确的位置

![image-20201015105115574](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015105115574.png)

![image-20201015105202440](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015105202440.png)

- 代码思路:
- **寻找枢纽：**用头尾中间位置的3个数据的中位数。

![image-20201015132407103](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015132407103.png)

![image-20201015110403326](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015110403326.png)

**利用指针：**

先将枢纽放到倒数第二个位置（因为在找枢纽的时候已经排过序将3个数中的最大数放到枢纽后面）

然后定义两个指针：left指向最开始的数据，right指向枢纽前一个数据

然后开始比较指针和枢纽的大小，left指针向左查找，一旦指针指向的数据大于枢纽，则left停止查找；

right指针向右查找，一旦指针指向的数据小于枢纽，则right停止查找。

然后将left和right指向的数据进行交换。

循环进行以上操作，直到left> =right 时，将left指向位置的数据和枢纽交换。

完成枢纽位置的确认，之后该枢纽的位置便是最终正确的排序的位置，不会再改变。

再次开始寻找枢纽，循环以上步骤，直到排序完成。

![image-20201015110607099](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015110607099.png)

**11:15**  pause

**13:30**  start  

- 代码实现：

  选择枢纽：

  首先是取出3个数据，最左边的和最右边（第一次进行选择就是位置0和位置是length-1处）假设取出来的数据是按照左中右：20，5，100，进行排序后左中右分别为5，20，100。（此时它们就是有序的）

  此时直接取出中间（center）值也就是三个数中的中位数，就可以找到枢纽20

  然后交换center和right前一个元素的位置，将center放到right前，（因为他们已经是有序的了，我们就不要把枢纽放在最后打乱顺序了）



![image-20201015133022614](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015133022614.png)

一开始：

![image-20201015133908535](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015133908535.png)

选择枢纽后：

![image-20201015133806108](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015133806108.png)

- 快速排序的代码：

  注:该代码有误，主要学习思想

![image-20201015143522586](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015143522586.png)

结果有误：

![image-20201015142301773](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015142301773.png)

![image-20201015135541394](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015135541394.png)

- 快速排序的效率：

![image-20201015135230742](C:\Users\yokoda\AppData\Roaming\Typora\typora-user-images\image-20201015135230742.png)

Day 06 结束 2020.10.15 14：40 进度：155P结束，整个视频结束。

****

