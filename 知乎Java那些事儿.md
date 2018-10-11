### 1.Integer   
Integer的作者写这个类时,为了避免重复创建对象,对Integer值做了缓存, 如果值在缓存范围内直接返回缓存好的对象,否则new一个对象返回.  IntegerCache这是一个内部静态类，该类只能在Integer这个类的内部访问， 这个类在初始化的时候，会去加载JVM的配置，如果有值，就用配置的值初始化缓存数组，  否则就缓存-128到127之间的值。

>结论：我们在比较两个Integer对象的值时，无论是怎么声明的，都一定要使用equals去比较，
        不能用==，在Java中没有重载操作符这一说，特别是从其它语言转到Java的童鞋们要注意。

### 2.string   
```java
String s1 = "100";
String s2 = "100";
System.out.println(s1==s2); //true
String s3 = new String("100");
String s4 = new String("100");
System.out.println(s3==s4);  //false
```
在JVM中，当代码执行到String s1 = "100" 时，会先看常量池里有没有字符串刚好是“100”这个对象，如果没有，在常量池里创建初始化该对象，并把引用指向它，如下图，绿色部分为常量池，存在于堆内存中。
当执行到String s2 = "100" 时，发现常量池已经有了100这个值，
于是不再在常量池中创建这个对象，而是把引用直接指向了该对象.
由于==是判断两个对象是否指向同一个引用，所以这儿打印出来的就应该是true。
继续执行到Strings3 = new String("100") 这时候我们加了一个new关键字，
这个关键字呢就是告诉JVM，你直接在堆内存里给我开辟一块新的内存.

>结论：我们在比较两个String对象内容时，无论是怎么声明的，都一定要使用equals去比较，不能用==， 在Java中没有重载操作符这一说，特别是从其它语言转到Java的童鞋们要注意。Java字符串两种声明方式在堆内存中不同的体现，我们在写代码过程中，为了避免重复的创建对象，尽量使用String s1 ="123" 而不是String s1 = new String("123")，因为JVM对前者给做了优化。

### 3.equals   
```java
String s3 = new String("100");
String s4 = new String("100");
System.out.println(s3.equals(s4));  //true
Integer itr = new Integer("123");
Long log = new Long("123");
System.out.println(itr.equals(log));  //false
Person p1 = new Person("张三");
Person p2 = new Person("张三");
System.out.println(p1.equals(p2));  //false
```
两者之间没有必然的联系，在引用类型中，"=="是比较两个引用是否指向堆内存里的同一个地址（同一个对象），而equals是一个普通的方法，该方法返回的结果依赖于自身的实现。
实体类的equals继承于Object类:
![equals](https://pic2.zhimg.com/80/v2-c4bf936500c8cd6056ea678357abf41a_hd.jpg "equals实现")   
所以代码person1.equals(person2)等同于person1 == person2，当然打印出来的结果是false。   
对于Integer类,equals的实现如下:   
![equals](https://pic2.zhimg.com/80/v2-9f75d738ca75f71317c3d9137fb01db9_hd.jpg)
当代码执行到System.out.println(itr.equals(lon))时，会判断传入的lon这个对象是否是Integer类型，这里的lon是Long类型，所以打印出来的结果当然是false了。   
String的equals实现:   
![equals](https://pic2.zhimg.com/80/v2-330cbd581df8d308946da6aabba0667f_hd.jpg)
当代码执行到：System.out.println(s3.equals(s4))，由于字符串底层char数组里存的都是{'1','0','0'}当然打印出来是true了。   

### 4.数组   

>概念:数组，是相同数据类型的元素按一定顺序排列的集合。   
数组的三种声明方法:   
![数组](https://pic3.zhimg.com/80/v2-35105f000b2343a3cb8053abdb0c6233_hd.jpg)
反编译后:
![反编译](https://pic3.zhimg.com/80/v2-ff2927f3ff98cd43cbbc3e18e6336ab2_hd.jpg)
三种数组的声明方式编译后，最后创建的方式都是一样的，都给我们加了new关键字，顺手还把charArr3的声明与赋值一体化了，编译器你管得也太多了吧。评论区里有人说反编译后和我反编译后的代码不一样，本专栏所有文章是基于JDK1.8讲解的，反编译工具是idea自带的反编译工具，不一样的原因可能是各位的JDK版本或反编译工具和我不一致。用IDE的代码联想功能看一下：
![联想](https://pic4.zhimg.com/80/v2-892060ceb35b218c1e7b8c9372a86881_hd.jpg)
Object类有的方法它都有，它还多了一个length属性（注意不是方法）。个人认为，在Java层面，我们完全可以把数组当成对象来看待，下图我们模拟一下数组在堆内存中的大致的样子，每一个数组都是按顺序排列在堆内存中，正因为如此，我们可以通过数组+[下标]的方式来直接访问数组里的元素。

二维数组:
![二维数组](https://pic1.zhimg.com/80/v2-8e1892a0c57b3a3d1ac11707c7356113_hd.jpg)   
反编译:   
![反编译](https://pic3.zhimg.com/80/v2-a44b7c61d53417c5b1fb62f9f5384eed_hd.jpg)   
图像表示:   
![表示](https://pic1.zhimg.com/80/v2-5ad580bf5b5b89b780fa67fe0dcca09d_hd.jpg)
