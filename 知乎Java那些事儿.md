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
