# Java

## 标识符

>给文件夹取名:全小写
>
>给类取名字:遵循大驼峰式 -> 每个单词首字母大写 (上级全是小写)
>
>给方法和变量取名字:遵循小驼峰式 -> 从第二个单词开始往后首字母大写

![ec7fa0cc5d14347a14693d3c66c0c7a.png](https://s2.loli.net/2024/11/20/9WzitZGVm5AfcH3.png)

## 快捷键

| 快捷键               | 功能                                   |
| -------------------- | -------------------------------------- |
| `Alt+Enter`          | 导入包，自动修正代码(重中之重)         |
| `Ctrl+Y`             | 删除光标所在行                         |
| `Ctrl+D`             | 复制光标所在行的内容，插入光标位置下面 |
| `Ctrl+Alt+L`         | 格式化代码                             |
| `Ctrl+/`             | 单行注释                               |
| `Ctrl+Shift+/`       | 选中代码注释，多行注释，再按取消注释   |
| `Alt+Shift+上下箭头` | 移动当前代码行                         |
| `Home` | 移动光标到行首|
| `End` | 移动光标到行尾|

## Scanner键盘录入

> **`Scanner 变量名 = new Scanner(System.in);`**
> 
> 调用方法,实现键盘录入
> `变量名.nextInt() 输入整数int型的`
> `变量名.next() 输入字符串  String型的  `

## Random生成随机数

> **`Random 变量名 = new Random()`**
>
> 调用方法,生成随机数:
> `变量名.nextInt() -> 在int的取值范围内随机一个整数`
>
> 在指定范围内随机一个数:
> `nextInt(int bound) -> 在0-(bound-1)`

## 数组

>动态初始化:
>**`数据类型[]  数组名= new 数据类型[长度]`** 
>
>静态初始化:
>**`数据类型[] 数组名 = {元素1,元素2...}`**
>
>获取数组长度:
>`数组名.length`
>
>存储元素
>`数组名[索引值] = 值`
>
>遍历数组
>`数组名.fori`
>增强for:`数组名.for`
>
>数组扩容与合并
>本质:创建一个新的数组对这个新的数组进行操作

## 方法

>通用定义格式(小驼峰):
>
>**`修饰符(默认public) 返回值类型(没有就void) 方法名(参数){`**
> **`方法体`**
> **`return 结果`**
>**`}`**
>
>使用方法: 对象名.方法名
>
>在API查询中如: `boolean contains(String s)` 第一个为返回类型 contains是方法名

## 面向对象
###  封装 bean 

>类名上@Data快速设置
>用private将属性封装起来,外界不能直接调用,保护了属性
>对外提供一套公共的接口(set/get方法),让外界通过公共的接口间接使用封装起来的属性
### this
>哪个对象调用的this所在的方法,this就代表哪个对象
### 标准java bean
>自己设置出的java bean可以当作数据类型如`List<User>`
>类必须是具体的(非抽象 abstract)和公共的，public class 类名
>
>**一个`@Data`全搞定**
>
>并且具有无参数的构造方法，有参构造
>成员变量私有化，并提供用来操作成员变量的`set` 和`get` 方法。 

### 可变参数
>数据类型...变量名
>需要放到最后
>
### 继承
>extends
>子父调用(多态):
>成员方法:看new的是谁,先调用谁中的方法,子类没有,找父类
>继承中,成员变量访问特点:看等号左边是谁,先调用谁中的成员变量
>成员方法访问特点:看new的是谁,先调用谁中的方法
### 抽象(接口的工具人)
>抽象方法:
>修饰符 abstract 返回值类型 方法名(参数);
>抽象类:
>`public  abstract class 类名{}`
>继承抽象类一定要重写其中的抽象方法
### 接口
>接口:是一个引用数据类型,是一种标准,规则
>interface 接口
>`public interface 接口名{}`
>implements 实现
>`实现类 implements 接口名{}`
### 实现类实现接口
>重写接口中的抽象方法
>创建实现类对象(接口不能直接new对象)
>调用重写的方法
>
>接口可以多继承 -> 一个接口可以继承多个接口
>`public interface InterfaceA extends InterfaceB,InterfaceC{}`
>接口可以多实现 -> 一个实现类可以实现一个或者多个接口
>`public class InterfaceImpl implements InterfaceA,InterfaceB{}`
>一个子类可以继承一个父类的同时实现一个或者多个接口
>`public class Zi extends Fu implements  InterfaceA,InterfaceB{}`
>继承也好,实现接口也罢,只要是父类中或者接口的抽象方法,子类或者实现类都要重写
### 多态
>父类引用指向子类对象(大哥的对象用小弟重写的方法)
>**`Fu fu = new Zi()`** -> 理解为大类型接收了一个小类型的数据
>
>成员变量看👈 方法看👉 (用的Zi的方法)
### 匿名内部类
>当简单调用一次接口中的方法,我们就可以使用匿名内部类
>`new 接口/抽象类(){`
>			`重写方法`
>`}.重写的方法();`
>
>==============================================================
>
>`类名 对象名 = new 接口/抽象类(){`
>			`重写方法`
>`};`
>`对象名.重写的方法();`

## 异常

````java
异常处理方式

1.throws

2.try...catch
      格式:
  try{

     可能出现异常的代码

  }catch(异常 对象名){

  处理异常的代码-> 将来开发会将异常信息保存到日志文件中

  }finally{
  		不管是否有异常,都会执行的代码
  }
````



## Object类

>所有类的根类(父类),所有的类都会直接或者间接继承Object类
>
>Object中的toString方法:返回该对象的字符串表示形式
>
>Object中的equals方法:比较两个对象的地址值是否相等

## 经典接口

### **java.lang.Comparable**

>哪个类的对象要比较大小，哪个类就实现`java.lang.Comparable`接口，并重写方法
>方法体就是你要如何比较当前对象和指定的另一个对象的大小
>对象比较大小时，通过对象调用compareTo方法，根据方法的返回值决定谁大谁小。
>
>比较**ASCII**码

````java
//如果students[i]比students[i+1]大,就排序换位置
   if (students[i].compareTo(students[i+1])>0){
   		Student temp = students[i];
      students[i] = students[i+1];
      students[i+1] = temp;
      }
````

### **java.util.Comparator**

>**编写一个类**，我们称之为比较器类型，实现`java.util.Comparator`接口，并重写方法
>方法体就是你要如何指定的两个对象的大小
>比较大小时，通过比较器类型的对象调用compare()方法，将要比较大小的两个对象作为compare方法的实参传入，根据方法的返回值决定谁大谁小。
>o1对象减o2大于0返回正整数
>o1对象减o2小于0返回负整数
>o1对象减o2等于0返回零

````java
/*
       o1代表students[i]
       o2代表students[i+1]

       如果o1的分数大于o2的分数-> compare方法返回正整数
       如果o1的分数小于o2的分数-> compare方法返回负整数
       如果o1的分数等于o2的分数-> compare方法返回0
     */
    @Override
    public int compare(Object o1, Object o2) {
        Student s1 = (Student) o1;
        Student s2 = (Student) o2;
        return s1.getScore()-s2.getScore();
    }
````

## 基础API

### String 字符串
>String的方法
>判断方法
>`boolean equals(String s) -> 比较字符串内容`
>`boolean equalsIgnoreCase(String s) -> 比较字符串内容,忽略大小写` 
>获取功能
>`int length() -> 获取字符串长度`
>`String concat(String s)-> 字符串拼接,返回新串儿`
>`char charAt(int index) -> 根据索引获取对应的字符`
>`int indexOf(String s) -> 获取指定字符串在大字符串中第一次出现的索引位置`
>`String subString(int beginIndex) -> 截取字符串,从指定索引开始截取到最后,返回新串儿`
>`String subString(int beginIndex,int endIndex) -> 截取字符串,从beginIndex开始到endIndex结束`
>分割功能
>`String[] split(String regex)->按照指定的规则分割字符串`
>注意:regex写的是正则表达式 -> . 在正则表达式中代表任意一个字符
>`boolean contains(String s) -> 判断老串儿中是否包含指定的串儿`
>`boolean endsWith(String s) -> 判断老串儿是否以指定的串儿结尾`
>`boolean startsWith(String s) -> 判断老串儿是否以指定的串儿开头`
>`String toLowerCase()-> 将字母转成小写`
>`String toUpperCase() -> 将字母转成大写`
>`String trim() -> 去掉字符串两端空格`
### StringBuilder类
>主要是字符串拼接
>StringBuilder,底层自带一个缓冲区(没有被final修饰的byte数组)拼接字符串之后都会在此缓冲区中保存,在拼接的过程中,不会随意产生新对象,节省内存
>`StringBuilder sb = new StringBuilder();`
>`StringBuilder()`
>`StringBuilder(String str) `
>`StringBuilder append(任意类型数据) -> 字符串拼接,返回的是StringBuilder自己`
>`StringBuilder reverse()-> 字符串翻转,返回的是StringBuilder自己`
>`String toString() -> 将StringBuilder转成String-> 用StringBuilder拼接字符串是为了效率,为了不占内存,那么拼完之后我们后续可能会对拼接好的字符串进行处理,就需要调用String中的方法,所以需要将StringBuilder转成String `
````java
public class Demo02StringBuilder {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();
        StringBuilder sb1 = sb.append("张无忌");
        System.out.println(sb1);
        System.out.println(sb);
        System.out.println(sb==sb1);

        System.out.println("==============");
        //链式调用
        sb.append("赵敏").append("周芷若").append("小昭");
        System.out.println(sb);

        sb.reverse();
        System.out.println(sb);

        String s = sb.toString();
        System.out.println(s);
    }
}
````

### Arrays数组工具类

| 方法                                                         | 说明                                    |
| ------------------------------------------------------------ | --------------------------------------- |
| `static String toString(int[] a)`<br>`Arrays.toString(数组名) ` | 按照格式打印数组元素[元素1, 元素2, ...] |
| `static void sort(int[] a)`<br>`Arrays.sort(数组名)`         | 升序排序                                |
| `static int binarySearch(int[] a, int key)`<br>`Arrays.binarySearch(数组名, value对应的key)` | 二分查找(前提是升序)                    |
| `static int[] copyOf(int[] original, int newLength)`<br>`Arrays.copyOf(数组名, 新数组长度)` | 数组扩容                                |
````java
public class Demo02Arrays {
    public static void main(String[] args) {
        int[] arr = {5,3,4,6,5,4,7};
        System.out.println(Arrays.toString(arr));

        System.out.println("==============");
        Arrays.sort(arr);
        System.out.println(Arrays.toString(arr));

        System.out.println("==============");
        int[] arr1 = {1,2,3,4,5,6,7};
        int index = Arrays.binarySearch(arr1, 3);
        System.out.println("index = " + index);

        System.out.println("==============");
        int[] arr2 = {1,2,3,4,5};
        int[] newArr = Arrays.copyOf(arr2, 10);
        System.out.println(Arrays.toString(newArr));
        
        arr2 = newArr;
        System.out.println(Arrays.toString(arr2));
        //[1, 2, 3, 4, 5, 0, 0, 0, 0, 0]

    }
}
````
### 包装类

>包装类不能直接使用+ - * /,所以需要将包装类转成基本类型,才能使用+ - * /
>
>将来有一些特定场景,特定操作,比如调用方法传递包装类

| 基本类型 | 包装类    |
| -------- | --------- |
| byte     | Byte      |
| short    | Short     |
| int      | Integer   |
| long     | Long      |
| float    | Float     |
| double   | Double    |
| char     | Charactor |
| boolean  | Boolean   |

### 字符串拼接

> 方式1: + 拼接

````java
		int i = 10;
		String s1 = i+"";//其他类型的+个空串就变成String类型的
		System.out.println(s1+1); 
101
````

> 方式2: String中的静态方法

````java
		String s = String.valueOf(10);
		System.out.println(s+1);
101
````

### Date类

````java
  Date() -> 获取当前系统时间
  Date(long time) -> 获取指定时间,传递毫秒值 -> 从时间原点开始算   
````

## 多线程

### 继承Thread创建线程的方式

> 1.定义一个类,继承Thread
> 2.重写run方法,在run方法中设置线程任务(所谓的线程任务指的是此线程要干的具体的事儿,具体执行的代码)

````java
public class MyThread extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println("MyThread...执行了"+i);
        }
    }
}
````

> 3.创建自定义线程类的对象 
> 4.调用Thread中的start方法,开启线程,jvm自动调用run方法

````java
public class Test01 {
    public static void main(String[] args) {
        //创建线程对象
        MyThread t1 = new MyThread();
        //调用start方法,开启线程,jvm自动调用run方法
        t1.start();

        for (int i = 0; i < 10; i++) {
            System.out.println("main线程..........执行了"+i);
        }
    }
}
````

### Thread类中的方法

> void start() -> 开启线程,jvm自动调用run方法
>
> void run()  -> 设置线程任务,这个run方法是Thread重写的接口Runnable中的run方法
> String getName()  -> 获取线程名字
>
> void setName(String name) -> 给线程设置名字
>
> static Thread currentThread() -> 获取正在执行的线程对象(此方法在哪个线程中使用,获取的就是哪个线程对象)
>
> static void sleep(long millis)->线程睡眠,超时后自动醒来继续执行,传递的是毫秒值
>
> void setPriority(int newPriority)   -> 设置线程优先级,优先级越高的线程,抢到CPU使用权的几率越大,但是不是每次都先抢到
>
> int getPriority()  -> 获取线程优先级
>
> void setDaemon(boolean on)  -> 设置为守护线程,当非守护线程执行完毕,守护线程就要结束,但是守护线程也不是立马结束,当非守护线程结束之后,系统会告诉守护线程人家结束了,你也结束吧,在告知的过程中,守护线程会执行,只不过执行到半路就结束了
>
> static void yield() -> 礼让线程,让当前线程让出CPU使用权
>
> void join() -> 插入线程或者叫做插队线程    

### 实现Runnable接口创建线程

> 1.创建类,实现Runnable接口
> 2.重写run方法,设置线程任务

````java
public class MyRunnable implements Runnable{    
	@Override    
	public void run() {        
	for (int i = 0; i < 10; i++) {            System.out.println(Thread.currentThread().getName()+"...执行了"+i);        		}    
	}
}
````

> 3.利用Thread类的构造方法:Thread(Runnable target),创建Thread对象(线程对象),将自定义的类当参数传递到Thread构造中 -> 这一步是让我们自己定义的类成为一个真正的线程类对象
> 4.调用Thread中的start方法,开启线程,jvm自动调用run方法 

````java
public class Test01 {
    public static void main(String[] args) {
        MyRunnable myRunnable = new MyRunnable();

        /*
           Thread(Runnable target)
         */
        Thread t1 = new Thread(myRunnable);
        //调用Thread中的start方法,开启线程
        t1.start();

        for (int i = 0; i < 10; i++) {
            System.out.println(Thread.currentThread().getName()+"...执行了"+i);
        }
    }
}
````

### 解决线程安全 同步代码块

> 1.格式:
>   `synchronized(任意对象){`
>       `线程可能出现不安全的代码`
>   `}`
> 2.任意对象:就是我们的锁对象
> 3.执行:
>   一个线程拿到锁之后,会进入到同步代码块中执行,在此期间,其他线程拿不到锁,就进不去同步代码块,需要在同步代码块外面等待排队,需要等着执行的线程执行完毕,出了同步代码块,相当于释放锁了,等待的线程才能抢到锁,才能进入到同步代码块中执行

### 解决线程安全 同步方法

#### 普通同步方法_非静态

> 1.格式:
>   `修饰符 synchronized 返回值类型 方法名(参数){`
>       `方法体`
>       `return 结果`
>   `}`
> 2.默认锁:this
#### 普通同步方法_静态
> 1.格式:
>   `修饰符 static synchronized 返回值类型 方法名(参数){`
>       `方法体`
>       `return 结果`
>   `}`
> 2.默认锁:class对象

### 线程之间的通信

| 方法               | 说明                                                         |
| ------------------ | ------------------------------------------------------------ |
| `void wait()`      | 线程等待,等待的过程中线程会释放锁,需要被其他线程调用notify方法将其唤醒,重新抢锁执行 |
| `void notify()`    | 线程唤醒,一次唤醒一个等待线程;如果有多条线程等待,则随机唤醒一条等待线程 |
| `void notifyAll()` | 唤醒所有等待线程                                             |

### Lock锁

> 1.概述:Lock是一个接口
> 2.实现类:ReentrantLock 
> 3.方法:
>   lock() 获取锁
>   unlock() 释放锁

````java
public class MyTicket implements Runnable {
    //定义100张票
    int ticket = 100;

    //创建Lock对象
    Lock lock = new ReentrantLock();

    @Override
    public void run() {
        while (true) {
            try {
                Thread.sleep(100L);

                //获取锁
                lock.lock();
                if (ticket > 0) {
                    System.out.println(Thread.currentThread().getName() + "买了第" + ticket + "张票");
                    ticket--;
                }
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }finally {
                //释放锁
                lock.unlock();
            }

        }
    }
}

````

````java
public class Test01 {
    public static void main(String[] args) {
        MyTicket myTicket = new MyTicket();

        Thread t1 = new Thread(myTicket, "赵四");
        Thread t2 = new Thread(myTicket, "刘能");
        Thread t3 = new Thread(myTicket, "广坤");

        t1.start();
        t2.start();
        t3.start();
    }
}
````

> synchronized:不管是同步代码块还是同步方法,都需要在结束一对{}之后,释放锁对象
> Lock:是通过两个方法控制需要被同步的代码,更灵活

### Callable接口实现多线程

> 1.概述:Callable<V>是一个接口,类似于Runnable
> 2.方法:
>   V call()  -> 设置线程任务的,类似于run方法
> 3.call方法和run方法的区别:
>   a.相同点:都是设置线程任务的
>   b.不同点:
>     call方法有返回值,而且有异常可以throws
>     run方法没有返回值,而且有异常不可以throws
>         
> 4.<V> 
>   a.<V>叫做泛型
>   b.泛型:用于指定我们操作什么类型的数据,<>中只能写引用数据类型,如果泛型不写,默认是Object类型数据
>   c.实现Callable接口时,指定泛型是什么类型的,重写的call方法返回值就是什么类型的
>       
> 5.获取call方法返回值: FutureTask<V>
>   a. FutureTask<V> 实现了一个接口: Future <V>
>   b. FutureTask<V>中有一个方法:
>      V get() -> 获取call方法的返回值

````java
public class Test {
    public static void main(String[] args) throws ExecutionException, InterruptedException {
        MyCallable myCallable = new MyCallable();
        /*
           FutureTask(Callable<V> callable)
         */
        FutureTask<String> futureTask = new FutureTask<>(myCallable);

        //创建Thread对象-> Thread(Runnable target)
        Thread t1 = new Thread(futureTask);
        t1.start();

        //调用get方法获取call方法返回值
        System.out.println(futureTask.get());
    }
}

````

````java
public class MyCallable implements Callable<String> {

    @Override
    public String call() throws Exception {
        return "涛哥和金莲...的故事";
    }
}
````

### 线程池实现多线程

> 1.如何创建线程池对象:用具类-> Executors
>
> 2.获取线程池对象:Executors中的静态方法:
> `static ExecutorService newFixedThreadPool(int nThreads)`
> a.参数:指定线程池中最多创建的线程对象条数
> b.返回值ExecutorService 是线程池,用来管理线程对象
>
> 3.执行线程任务: ExecutorService中的方法
> `Future<?> submit(Runnable task)` 提交一个Runnable任务用于执行 
> `Future<T> submit(Callable<T> task) `提交一个Callable任务用于执行 
> 4.submit方法的返回值:Future接口
> 用于接收run方法或者call方法返回值的,但是run方法没有返回值,所以可以不用     Future接收,执行call方法需要用Future接收
> Future中有一个方法:V get()  用于获取call方法返回值
>
> 5. ExecutorService中的方法:
>     `void shutdown() ` 启动有序关闭，其中先前提交的任务将被执行，但不会接受任何新任务

````java
public class MyRunnable implements Runnable{
    @Override
    public void run() {
        System.out.println(Thread.currentThread().getName()+"...执行了");
    }
}
````

````java
public class Test01 {
    public static void main(String[] args) {
        //创建线程池对象
        ExecutorService es = Executors.newFixedThreadPool(2);
        es.submit(new MyRunnable());
        es.submit(new MyRunnable());
        es.submit(new MyRunnable());

        //es.shutdown();//关闭线程池对象
    }
}
````

````java
public class MyCallable implements Callable<Integer> {
    @Override
    public Integer call() throws Exception {
        return 1;
    }
}
````

````java
public class Test02 {
    public static void main(String[] args) throws ExecutionException, InterruptedException {
        //创建线程池对象
        ExecutorService es = Executors.newFixedThreadPool(2);
        //Future<?> submit(Runnable task) 提交一个Runnable任务用于执行 
        //返回一个Future<?>对象
	    //Future<T> submit(Callable<T> task) 提交一个Callable任务用于执行
        //返回一个Future<T>对象
        Future<Integer> future = es.submit(new MyCallable());
        System.out.println(future.get());
    }
}
````

### 定时器_Timer

> 1.概述:定时器
> 2.构造:
>   `Timer()`
> 3.方法:
>   `void schedule(TimerTask task, Date firstTime, long period)  `
>                 task:抽象类,是Runnable的实现类
>                 firstTime:从什么时间开始执行
>                 period: 每隔多长时间执行一次,设置的是毫秒值    

## 集合

![99733802a30eec5b81cc2bff89adfca.png](https://s2.loli.net/2024/11/20/j9ockhLCQsMBYlX.png)

> 单列集合:一个元素就一个组成部分:
>
> 双列集合:一个元素有两部分构成:  key 和 value

### Collection接口

````java
1.概述:单列集合的顶级接口
2.使用:
  a.创建:

    Collection<E> 对象名 = new 实现类对象<E>()
        
  b.<E>:泛型,决定了集合中能存储什么类型的数据,可以统一元素类型
        泛型中只能写引用数据类型(类，接口，数组),如果不写,默认Object类型,此时什么类型的数据都可以存储了
        <int> 不行
        <Integer> 行
        <Person> 行
      
  c.泛型细节:
    我们等号前面的泛型必须写,等号后面的泛型可以不写,jvm会根据前面的泛型推导出后面的泛型是啥
      
3.常用方法:
  boolean add(E e) : 将给定的元素添加到当前集合中(我们一般调add时,不用boolean接收,因为add一定会成功)
  boolean addAll(Collection<? extends E> c) :将另一个集合元素添加到当前集合中 (集合合并)
  void clear():清除集合中所有的元素
  boolean contains(Object o)  :判断当前集合中是否包含指定的元素
  boolean isEmpty() : 判断当前集合中是否有元素->判断集合是否为空
  boolean remove(Object o):将指定的元素从集合中删除
  int size() :返回集合中的元素个数。
  Object[] toArray(): 把集合中的元素,存储到数组中  
````

### List接口

````java
1.概述:是Collection接口的子接口
2.常见的实现类:
  ArrayList LinkedList Vector
````

### ArrayList集合

````java
1.概述:ArrayList是List接口的实现类
2.特点:
  a.元素有序-> 按照什么顺序存的,就按照什么顺序取
  b.元素可重复
  c.有索引-> 可以利用索引去操作元素
  d.线程不安全
      
3.数据结构:数组       
4.常用方法:
  boolean add(E e)  -> 将元素添加到集合中->尾部(add方法一定能添加成功的,所以我们不用boolean接收返回值)
  void add(int index, E element) ->在指定索引位置上添加元素
  boolean remove(Object o) ->删除指定的元素,删除成功为true,失败为false
  E remove(int index) -> 删除指定索引位置上的元素,返回的是被删除的那个元素
  E set(int index, E element) -> 将指定索引位置上的元素,修改成后面的element元素
  E get(int index) -> 根据索引获取元素
  int size()  -> 获取集合元素个数
````

### LinkedList集合

````java
1.概述:LinkedList是List接口的实现类
2.特点:
  a.元素有序
  b.元素可重复
  c.有索引 -> 这里说的有索引仅仅指的是有操作索引的方法,不代表本质上具有索引
  d.线程不安全
      
3.数据结构:双向链表      
    
4.方法:有大量直接操作首尾元素的方法
  - public void addFirst(E e):将指定元素插入此列表的开头。
  - public void addLast(E e):将指定元素添加到此列表的结尾。
  - public E getFirst():返回此列表的第一个元素。
  - public E getLast():返回此列表的最后一个元素。
  - public E removeFirst():移除并返回此列表的第一个元素。
  - public E removeLast():移除并返回此列表的最后一个元素。
  - public E pop():从此列表所表示的堆栈处弹出一个元素。
  - public void push(E e):将元素推入此列表所表示的堆栈。
  - public boolean isEmpty()：如果列表没有元素，则返回true。
````

### 增强for

````java
1.作用:
  遍历集合或者数组
2.格式:
  for(元素类型 变量名:要遍历的集合名或者数组名){
      变量名就是代表的每一个元素
  }

3.快捷键:集合名或者数组名.for
````

### Collections集合工具类

````java
1.概述:集合工具类
2.特点:
  a.构造私有
  b.方法都是静态的
      
3.使用:类名直接调用
    
4.方法:
  static <T> boolean addAll(Collection<? super T> c, T... elements)->批量添加元素 
  static void shuffle(List<?> list) ->将集合中的元素顺序打乱
  static <T> void sort(List<T> list) ->将集合中的元素按照默认规则排序
  static <T> void sort(List<T> list, Comparator<? super T> c)->将集合中的元素按照指定规则排序 
````

````java
1.方法:static <T> void sort(List<T> list, Comparator<? super T> c)->将集合中的元素按照指定规则排序
    
2.Comparator比较器
  a.方法:
    int compare(T o1,T o2)
                o1-o2 -> 升序
                o2-o1 -> 降序   
````

````java
1.接口:Comparable接口
2.方法: int compareTo(T o) -> this-o (升序)   o-this(降序)
````

````java
Arrays中的静态方法:
static <T> List<T> asList(T...a) -> 直接指定元素,转存到list集合中
````

### Set集合

> Set接口并没有对Collection接口进行功能上的扩充,
>
> 而且所有的Set集合底层都是依靠Map实现

>Set和Map密切相关的
>Map的遍历需要先变成单列集合,只能变成set集合

#### HashSet集合的介绍和使用

````java
1.概述:HashSet是Set接口的实现类
2.特点:
  a.元素唯一
  b.元素无序
  c.无索引
  d.线程不安全
3.数据结构:哈希表
  a.jdk8之前:哈希表 = 数组+链表
  b.jdk8之后:哈希表 = 数组+链表+红黑树
            加入红黑树目的:查询快
4.方法:和Collection一样
5.遍历:
  a.增强for
  b.迭代器
````

#### LinkedHashSet的介绍以及使用

````java
1.概述:LinkedHashSet extends HashSet
2.特点:
  a.元素唯一
  b.元素有序
  c.无索引
  d.线程不安全
3.数据结构:
  哈希表+双向链表
4.使用:和HashSet一样     
````

### Map集合

> 1.概述:是双列集合的顶级接口
> 2.元素特点:
>   元素都是由key(键),value(值)组成 -> 键值对

#### HashMap的介绍和使用

````java
1.概述:HashMap是Map的实现类
2.特点:
  a.key唯一,value可重复 -> 如果key重复了,会发生value覆盖
  b.无序
  c.无索引
  d.线程不安全
  e.可以存null键null值
3.数据结构:
  哈希表
4.方法:
  V put(K key, V value)  -> 添加元素,返回的是
  V remove(Object key)  ->根据key删除键值对,返回的是被删除的value
  V get(Object key) -> 根据key获取value
  boolean containsKey(Object key)  -> 判断集合中是否包含指定的key
  Collection<V> values() -> 获取集合中所有的value,转存到Collection集合中
      
  Set<K> keySet()->将Map中的key获取出来,转存到Set集合中  
  Set<Map.Entry<K,V>> entrySet()->获取Map集合中的键值对,转存到Set集合中
````

````java
1.概述:LinkedHashMap extends HashMap
2.特点:
  a.key唯一,value可重复 -> 如果key重复了,会发生value覆盖
  b.有序
  c.无索引
  d.线程不安全
  e.可以存null键null值
3.数据结构:
  哈希表+双向链表
4.使用:和HashMap一样     
````

#### HashMap的两种遍历方式

##### 方式1:获取key,根据key再获取value

````java
Set<K> keySet()->将Map中的key获取出来,转存到Set集合中  
````

##### 方式2:同时获取key和value

````java
Set<Map.Entry<K,V>> entrySet()->获取Map集合中的键值对,转存到Set集合中
````

### TreeSet

````java
1.概述:TreeSet是Set的实现类
2.特点:
  a.对元素进行排序
  b.无索引
  c.不能存null
  d.线程不安全
  e.元素唯一
3.数据结构:红黑树      
````

````java
构造:
  TreeSet() -> 构造一个新的空 set，该 set 根据其元素的自然顺序进行排序 -> ASCII 
  TreeSet(Comparator<? super E> comparator)构造一个新的空 TreeSet，它根据指定比较器进行排序     
````

### TreeMap

````java
1.概述:TreeMap是Map的实现类
2.特点:
  a.对key进行排序
  b.无索引
  c.key唯一
  d.线程不安全
  e.不能存null
3.数据结构:红黑树      
````

````java
构造:
  TreeMap() -> 使用键的自然顺序构造一个新的、空的树映射 -> ASCII 
  TreeMap(Comparator<? super E> comparator)构造一个新的、空的树映射，该映射根据给定比较器进行排序
````

## IO流

### File类

````java
1.概述:文件和目录(文件夹)路径名的抽象表示   
2.简单理解:
  我们在创建File对象的时候,需要传递一个路径,这个路径定为到哪个文件或者文件夹上,我们的File就代表哪个对象
  File file = new File("E:\Idea\io\1.jpg")    
````

#### File的构造方法

````java
File(String parent, String child) 根据所填写的路径创建File对象
     parent:父路径
     child:子路径
File(File parent, String child)  根据所填写的路径创建File对象
     parent:父路径,是一个File对象
     child:子路径
File(String pathname)  根据所填写的路径创建File对象
     pathname:直接指定路径   
````

#### File的获取方法

````java
String getAbsolutePath() -> 获取File的绝对路径->带盘符的路径
String getPath() ->获取的是封装路径->new File对象的时候写的啥路径,获取的就是啥路径
String getName()  -> 获取的是文件或者文件夹名称
long length() -> 获取的是文件的长度 -> 文件的字节数   
````

#### File的创建方法

````java
boolean createNewFile()  -> 创建文件
        如果要创建的文件之前有,创建失败,返回false
        如果要创建的文件之前没有,创建成功,返回true
    
boolean mkdirs() -> 创建文件夹(目录)既可以创建多级文件夹,还可以创建单级文件夹
        如果要创建的文件夹之前有,创建失败,返回false
        如果要创建的文件夹之前没有,创建成功,返回true
````

#### File类的删除方法

````JAVA
boolean delete()->删除文件或者文件夹

注意:
  1.如果删除文件,不走回收站
  2.如果删除文件夹,必须是空文件夹,而且也不走回收站    
````

#### File的遍历方法

````JAVA
String[] list() -> 遍历指定的文件夹,返回的是String数组 
File[] listFiles()-> 遍历指定的文件夹,返回的是File数组 ->这个推荐使用
    
细节:listFiles方法底层还是list方法
     调用list方法,遍历文件夹,返回一个Stirng数组,遍历数组,将数组中的内容一个一个封装到File对象中,然后再将File对象放到File数组中
````

#### 相对路径和绝对路径

````JAVA
1.绝对路径:从盘符开始写的路径
  E:\\idea\\io\\1.txt
2.相对路径:不从盘符名开始写的路径
    
3.针对idea中写相对路径:
  a.口诀:哪个路径是参照路径,哪个路径就可以省略不写,剩下的就是在idea中的相对路径写法
        在idea中参照路径其实就是当前project的绝对路径
      
  b.比如:在module21下创建了一个1.txt
    先找1.txt的绝对路径:E:\Idea\idea2022\workspace\javase\module21\1.txt
    再找参照路径:E:\Idea\idea2022\workspace\javase
    参照路径可以省略:module21\1.txt
        
4.总结:
  在idea中写的相对路径,其实就是从模块名开始写
      
5.注意:
  如果直接写一个文件名1.txt,它所在的位置默认是在当前project下
````

### IO流分类

````JAVA
字节流:万能流,一切皆字节
      字节输出流:  OutputStream 抽象类
      字节输入流:  InputStream 抽象类
          
字符流:专门操作文本文档
      字符输出流:Writer 抽象类
      字符输入流:Reader 抽象类
````

### 字节流

#### OutputStream子类[FileOutputStream]

````java
1.概述:字节输出流,OutputStream 是一个抽象类
        子类: FileOutputStream
 2.作用:往硬盘上写数据
     
 3.构造:
   FileOutputStream(File file) 
   FileOutputStream(String name)
       
 4.特点:
   a.指定的文件如果没有,输出流会自动创建
   b.每执行一次,默认都会创建一个新的文件,覆盖老文件 
       
 5.方法:
   void write(int b)  一次写一个字节
   void write(byte[] b)  一次写一个字节数组
   void write(byte[] b, int off, int len)  一次写一个字节数组一部分 
             b:写的数组
             off:从数组的哪个索引开始写
             len:写多少个
   void close()  -> 关闭资源 
````

#### InputStream子类[FileInputStream]

````java
1.概述:字节输入流 InputStream ,是一个抽象类
      子类:FileInputStream
          
2.作用:读数据,将数据从硬盘上读到内存中来
    
3.构造:
  FileInputStream(File file)
  FileInputStream(String path)  
      
4.方法:
  int read()   一次读一个字节,返回的是读取的字节
  int read(byte[] b)  一次读取一个字节数组,返回的是读取的字节个数
  int read(byte[] b, int off, int len)  一次读取一个字节数组一部分,返回的是读取的字节个数
  void close()  关闭资源   
````

#### 字节流实现图片复制代码实现

````java
public class Demo01CopyFile {
    public static void main(String[] args)throws Exception {
        //1.创建FileInputStream
        FileInputStream fis = new FileInputStream("E:\\Idea\\io\\24.jpg");
        //2.创建一个FileOutputStream,将读取的图片写到指定的位置
        FileOutputStream fos = new FileOutputStream("E:\\Idea\\io\\大姐.jpg");
        //3.定义一个数组
        byte[] bytes = new byte[1024];
        //4.边读边写
        int len;
        //返回给len的是读取的字节个数 不等于-1就while循环写
        //文件读完了就返回-1
        while((len = fis.read(bytes))!=-1){
            fos.write(bytes,0,len);//读多少个,写多少个
        }
        //5.关流  先开后关
        fos.close();
        fis.close();
    }
}
````

### 字符流

#### FileReader

````java
1.概述:字符输入流 -> Reader -> 是一个抽象类
      子类:FileReader
2.作用:将文本文档中的内容读取到内存中来
3.构造:
  FileReader(File file)
  FileReader(String path)
4.方法:
  int read() -> 一次读取一个字符,返回的是读取字符对应的int值 
  int read(char[] cbuf) -> 一次读取一个字符数组,返回的是读取个数  
  int read(char[] cbuf, int off, int len) -> 一次读取一个字符数组一部分,返回的是读取个数
           cbuf:读取的数组
           off:从数组的哪个索引开始读
           len:读多少个
  void close() -> 关闭资源    
````

#### FileWriter

````java
1.概述:字符输出流 -> Writer -> 抽象类
  子类:FileWriter
2.作用:将数据写到文件中
3.构造:
  FileWriter(File file) 
  FileWriter(String fileName)     
  FileWriter(String fileName, boolean append) -> 追加,续写 
4.方法:
  void write(int c) -> 一次写一个字符 
  void write(char[] cbuf) 一次写一个字符数组 
  void write(char[] cbuf, int off, int len) 一次写一个字符数组一部分  
  void write(String str) 直接写一个字符串
  void flush()  :将缓冲区中的数据刷到文件中    
  void close()  关流
      
5.注意:FileWriterr底层自带一个缓冲区,我们写的数据会先保存到缓冲区中,所以我们需要将缓冲区中的数据刷到文件中 
````

#### FileWriter的刷新功能和关闭功能

````java
flush():将缓冲区中的数据刷到文件中,后续流对象还能继续使用
close():先刷新后关闭,后续流对象不能使用了   
````

### IO流异常处理方式

````java
1.格式:
  try(IO对象){
      可能出现异常的代码
  }catch(异常类型 对象名){
      处理异常
  }
2.注意:
  以上格式处理IO异常,会自动关流
````

### 字节缓冲流

````java
1.为啥要学字节缓冲流
  之前所写的FileOutputStream,FileInputStream,FileReader,FileWriter这都叫做基本类,其中FileInputStream和FileOutputStream的读写方法都是本地方法(方法声明上带native),本地方法是和系统以及硬盘打交道的,也就是说这两个对象的读和写都是在硬盘之间进行读写的,效率不高;缓冲流中底层带一个长度为8192的数组(缓冲区),此时读和写都是在内存中完成的(在缓冲区之间完成),内存中的读写效率非常高
    
   使用之前需要将基本流包装成缓冲流,其实就new对象时,传递基本流 
    
2.字节缓冲流
  a.BufferedOutputStream:字节缓冲输出流
    构造:BufferedOutputStream(OutputStream out)
    使用:和FileOutputStream一样
        
  b.BufferedInputStream:字节缓冲输入流
    构造:BufferedInputStream(InputStream in)
    使用:和FileInputStream一样   
````

### 字符缓冲流

````java
我们知道,字符流的基本流底层是有缓冲区的,所以在效率这一块效果不是特别明显,但是不代表不重要,因为我们应该主要学字符缓冲流的两个特有方法
````

#### 字符缓冲输出流BufferedWriter

````java
1.构造:
  BufferedWriter(Writer w)
2.方法:
  用起来和FileWriter一样
3.特有方法:
  newLine() 换行
````

#### 字符缓冲输入流BufferedReader

````java
1.构造:
  BufferedReader(Reader r)
2.方法:
  用法和FileReader一样
3.特有方法:
  String readLine()-> 一次读一行,如果读到结束标记,返回的是null
````

### 转换流

#### 转换流InputStreamReader

````java
1.概述:是字节流通向字符流的桥梁 -> 读数据
2.构造:
  InputStreamReader(InputStream in,String charsetName)
                                   charsetName:指定编码,不区分大小写
3.作用:
  可以直接指定编码,按照指定的编码去读内容
4.用法:
  基本用法和FileReader一样
````

#### 转换流OutputStreamWriter

````java
1.概述:是字符流通向字节流的桥梁
2.构造:
  OutputStreamWriter(OutputStream out,String charsetName)
                   
3.作用:
  按照指定的编码规则去存数据
      
4.用法:
  和FileWriter一样
````

### 序列化流

````java
1.作用:读写对象
2.两个对象:
  a.ObjectOutputStream -> 序列化流 -> 写对象
  b.ObjectInputStream -> 反序列化流 -> 读对象  
3.注意:
  我们将对象序列化到文件中,我们打开文件看不懂,这就对了,很多时候,我们操作的数据不能随便让别人看懂,不然别人就随意改动了,我们只需要将这些看不懂的内容成功读回来即可
      
  应用场景:比如玩儿游戏会对英雄存档,那么退出的时候英雄变成对象,将人物的属性变成对象的成员变量值,然后存到文件中,再次打开游戏,直接从文件中将这些人物对象读回来,将对象以及对象中的属性还原    
````

#### 序列化流ObjectOutputStream

````java
1.作用:写对象
2.构造:
  ObjectOutputStream(OutputStream out)
3.方法:
  writeObject(Object obj) -> 写对象
4.注意:
  想要将对象序列化到文件中,被序列化的对象需要实现Serializable接口
````

#### 反序列化流ObjectInputStream

````java
1.作用:读对象
2.构造:
  ObjectInputStream(InputStream in)
3.方法:
  Object readObject()
````

### Commons-io工具包

````java
IOUtils类
- 静态方法：IOUtils.copy(InputStream in,OutputStream out)传递字节流，实现文件复制。
- 静态方法：IOUtils.closeQuietly(任意流对象)悄悄的释放资源，自动处理close()方法抛出的异常。
````
````java
public class Demo01IOUtils {
    public static void main(String[] args) /*throws Exception*/{
        //- 静态方法：IOUtils.copy(InputStream in,OutputStream out)传递字节流，实现文件复制。
        //IOUtils.copy(new FileInputStream("E:\\Idea\\io\\8.jpg"),new FileOutputStream("E:\\Idea\\io\\孝敏.jpg"));
        //- 静态方法：IOUtils.closeQuietly(任意流对象)悄悄的释放资源，自动处理close()方法抛出的异常。
        FileWriter fw = null;
        try{
            fw = new FileWriter("module22\\commons.txt");
            fw.write("你好");
        }catch (Exception e){
            e.printStackTrace();
        }finally {
            if (fw!=null){
                IOUtils.closeQuietly(fw);
            }
        }
    }
}
````

````java
FileUtils类

- 静态方法：FileUtils.copyDirectoryToDirectory(File src,File dest);
           传递File类型的目录，进行整个目录的复制，自动进行递归遍历。
           
           参数:
             src:要复制的文件夹路径
             dest:要将文件夹粘贴到哪里去
             
- 静态方法：writeStringToFile(File file,String str)写字符串到文本文件中。
- 静态方法：String readFileToString(File file)读取文本文件，返回字符串。
````
````java
public class Demo02FileUtils {
    public static void main(String[] args)throws Exception {
       /* - 静态方法：FileUtils.copyDirectoryToDirectory(File src,File dest);
        传递File类型的目录，进行整个目录的复制，自动进行递归遍历。

        参数:
        src:要复制的文件夹路径
        dest:要将文件夹粘贴到哪里去*/
        //FileUtils.copyDirectoryToDirectory(new File("E:\\Idea\\io\\aa"),new File("E:\\Idea\\io\\cc"));

        //- 静态方法：writeStringToFile(File file,String str)写字符串到文本文件中。
        //FileUtils.writeStringToFile(new File("module22\\commons.txt"),"haha");
        //- 静态方法：String readFileToString(File file)读取文本文件，返回字符串。
        String s = FileUtils.readFileToString(new File("module22\\commons.txt"));
        System.out.println(s);
    }
}
````

### 快速记忆IO
![1705913137595.png](https://s2.loli.net/2024/11/20/s4OwyJFqAijNTKz.png)

## 网络编程

````java
[协议]
     TCP:面向连接协议
         需要先确认连接,才能进行数据交互
         好处:数据安全,能给数据的传输提供一个安全的传输环境
         坏处:效率低
     
     UDP:面向无连接协议
         好处:效率高
         坏处:传输的数据不安全,容易丢失数据包

[端口号]
   每一个应用程序的唯一标识
  
  用两个字节表示的整数，它的取值范围是0~65535。其中，0~1023之间的端口号用于一些知名的网络服务和应用，普通的应用程序需要使用1024以上的端口号。如果端口号被另外一个服务或应用所占用，会导致当前程序启动失败。
````

#### UDP协议编程

````java
1.DatagramSocket -> 好比寄快递找的快递公司
2.DatagramPacket -> 好比快递公司打包
````

##### 客户端(发送端)

````java
1.创建DatagramSocket对象(快递公司)
  a.空参:端口号从可用的端口号中随机一个使用
  b.有参:自己指定
2.创建DatagramPacket对象,将数据进行打包
  a.要发送的数据-> byte[]
  b.指定接收端的IP
  c.指定接收端的端口号
3.发送数据
4.释放资源
````

````java
直接执行发现,发送端在没有接收端的情况下,不会报错,因为UDP协议是面向无连接协议,不管有没有接收端,照发不误
````

##### 服务端(接收端)

````java
1.创建DatagramSocket对象,指定服务端的端口号
2.接收数据包
3.解析数据包
4.释放资源  
````

#### TCP协议编程

##### 编写客户端

````java
1.创建Socket对象,指明服务端的ip以及端口号
2.调用socket中的getOutputStream,往服务端发送请求
3.调用socket中的getInputStream,读取服务端响应回来的数据
4.关流
````

##### 编写服务端

````java
1.创建ServerSocket对象,设置端口号
2.调用ServerSocket中的accept方法,等待客户端连接,返回Socket对象
3.调用socket中的getInputStream,用于读取客户端发送过来的数据
4.调用socket中的getOutputStream,用于给客户端响应数据
5.关闭资源
````

#### 文件上传

````java
public class Client {
    public static void main(String[] args)throws Exception {
        //1.创建Socket对象
        Socket socket = new Socket("127.0.0.1", 6666);
        //2.创建FileInputStream,用于读取本地上的图片
        FileInputStream fis = new FileInputStream("E:\\Idea\\io\\24.jpg");
        //3.调用getOutputStream,用于将读取过来的图片写给服务端
        OutputStream os = socket.getOutputStream();
        //4.边读边写
        byte[] bytes = new byte[1024];
        int len;
        while((len = fis.read(bytes))!=-1){
            os.write(bytes,0,len);
        }

        //给服务端写一个结束标记
        socket.shutdownOutput();
        System.out.println("======以下代码是读取响应的结果======");

        //5.调用getInputStream,读取响应结果
        InputStream is = socket.getInputStream();
        byte[] bytes1 = new byte[1024];
        int len1 = is.read(bytes1);
        System.out.println(new String(bytes1,0,len1));

        //6.关流
        is.close();
        os.close();
        fis.close();
        socket.close();
    }
}

````

````java
public class Server {
    public static void main(String[] args)throws Exception {
        //1.创建ServerSocket对象
        ServerSocket ss = new ServerSocket(6666);
        //2.调用accept方法等待客户端的连接
        Socket socket = ss.accept();
        //3.调用socket中的getInputStream,读取客户端发送过来的图片
        InputStream is = socket.getInputStream();

        /*
          UUID调用randomUUID(),再调用toString,将其转成String
         */
        String s = UUID.randomUUID().toString();
        String name = s + System.currentTimeMillis();

        //4.创建FileOutputStream,将读取过来的图片写到硬盘上
        FileOutputStream fos = new FileOutputStream("E:\\Idea\\io\\upload\\"+name+".jpg");
        //5.边读边写
        byte[] bytes = new byte[1024];
        int len;
        while((len = is.read(bytes))!=-1){
            fos.write(bytes,0,len);
        }

        System.out.println("======以下代码是给客户端的响应结果======");

        //6.调用socket中的getOutputStream,给客户端响应结果
        OutputStream os = socket.getOutputStream();
        os.write("上传成功".getBytes());
        //7.关流
        os.close();
        fos.close();
        is.close();
        socket.close();
        ss.close();
    }
}
````

````java
public class Demo01UUID {
 public static void main(String[] args) {
     String string = UUID.randomUUID().toString();//生成一个十六进制的随机数
     System.out.println("string = " + string);
 }
}
````

## Lambda表达式

````java
Lambda表达式:
  a.定义格式:
    ()->{}
  b.各部分解释:
    () : 重写方法的参数位置
    -> : 将参数传递到方法体中
    {} : 重写方法的方法体    
````

````java
1.Lambda表达式怎么写(涛哥给的新手秘籍)
  a.观察是否是函数式接口做方法参数传递
  b.如果是,考虑使用Lambda表达式
  c.调用方法,以匿名内部类的形式传递实参
  d.从new接口开始到重写方法的方法名结束,选中,删除,别忘记再删除一个右半个大括号
  e.在重写方法的参数后面,方法体的大括号前面加上 -> 
    
    
2.省略规则:
  a.重写方法的参数类型可以干掉
  b.如果重写方法只有一个参数,所在的小括号可以干掉
  c.如果方法体中只有一句话,那么所在的大括号以及分号可以干掉
  d.如果方法体中只有一句话并且带return的,那么所在的大括号,分号以及return 可以干掉
````

````java
public class Demo03Lambda {
    public static void main(String[] args) {
        ArrayList<Person> list = new ArrayList<>();
        list.add(new Person("张三",10));
        list.add(new Person("李四",8));
        list.add(new Person("王五",9));

       /* Collections.sort(list, new Comparator<Person>() {
            @Override
            public int compare(Person o1, Person o2) {
                return o1.getAge()-o2.getAge();
            }
        });
*/
        System.out.println("=============Lambda==========");

      /*  Collections.sort(list,(Person o1, Person o2)-> {
                return o1.getAge()-o2.getAge();
        });*/

        System.out.println("===========Lambda表达式简化形式==========");

        Collections.sort(list,(o1, o2)-> o1.getAge()-o2.getAge());
        System.out.println(list);
    }
}

````



## 枚举

### 枚举介绍

```java
1.概述:五大引用数据类型:
      类 数组 接口 注解 枚举
          
2.定义:
  public enum 枚举类名{
      
  }
  所有的枚举类父类都是Enum
      
3.定义枚举值:
  a.枚举值特点:都是static final,但是定义的时候不要写出来,写出来报错
             写完所有的枚举值之后,最后加个;
             枚举值名字要大写 -> 开发习惯
                 
  b.使用:类名直接调用
      
  c.注意:每一个枚举值都是当前枚举类的对象    
      
4.问题:枚举类中的枚举值都是什么类型的?
  本类类型
    
5.枚举类中其他成员:构造
  在枚举类中定义的构造,默认都是private的
    
6.枚举类的使用场景:
  表示对象的状态
```

```java
public enum State {
    //State WEIFUKUAN = new State()
    //State WEIFUKUAN = new State("未付款")
    WEIFUKUAN("未付款"),
    //State YIFUKUAN = new State()
    //State YIFUKUAN = new State("已付款")
    YIFUKUAN("已付款"),
    //State WEIFAHUO = new State()
    //State WEIFAHUO = new State("未发货")
    WEIFAHUO("未发货"),
    //State YIFAHUO = new State()
    //State YIFAHUO = new State("已发货")
    YIFAHUO("已发货");

    private String name;

    private State() {

    }

    State(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

```

```java
public class Test01 {
    public static void main(String[] args) {
        State weifahuo = State.WEIFAHUO;
        System.out.println(weifahuo);//默认调用toString

        State yifukuan = State.YIFUKUAN;
        System.out.println(yifukuan.getName());

    }
}
```

### 枚举的方法_Enum

| 方法名              | 说明                     |
| ------------------- | ------------------------ |
| String toString()   | 返回枚举值的名字         |
| values()            | 返回所有与的枚举值       |
| valueOf(String str) | 将一个字符串转成枚举类型 |

```java
public enum State {
    //State WEIFUKUAN = new State()
    WEIFUKUAN("未付款"),
    //State YIFUKUAN = new State()
    YIFUKUAN("已付款"),
    //State WEIFAHUO = new State()
    WEIFAHUO("未发货"),
    //State YIFAHUO = new State()
    YIFAHUO("已发货");

    private String name;

    private State() {

    }

    State(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

```

```java
public class Test01 {
    public static void main(String[] args) {
        State weifahuo = State.WEIFAHUO;
        System.out.println(weifahuo);//默认调用toString

        State yifukuan = State.YIFUKUAN;
        System.out.println(yifukuan.getName());

        System.out.println("====================");

        String string = State.WEIFUKUAN.toString();
        System.out.println("string = " + string);

        System.out.println("===================");
        State[] values = State.values();
        for (State value : values) {
            System.out.println(value);
        }

        System.out.println("==================");

        State yifahuo = State.valueOf("YIFAHUO");
        System.out.println("yifahuo = " + yifahuo);
    }
}

```
