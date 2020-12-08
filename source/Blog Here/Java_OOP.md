# Java_OOP

> Object Oriented Programming

## 面向对象是基于面向过程的编程思想
    - 面向过程:强调的是每一个功能步骤
    - 面向对象:强调的是对象，然后由对象去调用功能

## 特征
    - 封装
    - 继承
    - 多态    

## Java中最基础的单位是类，类是Java中最基础的单位    
### 类
- 类就是一组相关的属性和行为的集合  
- 对象:是该类事物的具体表现形式，具体存在的个体  
    - 定义格式
    ~~~
    class 类名{
        类体;
    }
    ~~~
     > 当类名由多个单词组成的时候，要求每个单词的首字母大小，也就是大驼峰命名法
- 对象
    - 对象(Object)是类的实例                                     
    - 对象的创建称之为类的实例化
        - 语法
        new 类名;
        例如:new Person(); - 匿名对象
        
        - 使用方式
        对象创建的行的是叫做类的实例化，而串讲对象的本质就是在内存空间中的
        地区申请一块空间，用于记录该对象拥有的成员变量的信息。
### 引用的使用
使用引用数据类型声明的变量叫做引用类型变量，简称为“引用”

    1.<语法格式>
    类名 引用名称;
    Person p;
    2.<使用方式>
    引用变量通常用于记录创建对象在堆区中的内存地址信息，从而可以方便地使用
    该对象以及该对象中的成员变量信息，具体:  
    引用名.成员变量名;  
    如:
    Person p = new Person();
    p.name = '白菜';
    p.age = 18;

### 成员方法
类中可以定义成员变量和成员方法
- 返回值类型:是指从方法体中向方法体外返回的数据类型
- 形参列表:形式参数主要指从方法体外向方法体内传入数据内容，通过使用变量的声明来传入
    - 格式 -> 数据类型形参变量名
- 成员方法体
成员方法体通过用于编写描述该方法功能的语句块，也就是对多条语句的打包/包装。

- 调用  
    - 格式:引用/对象.成员方法名(实参列表)
    - 使用方法:实参列表主要用于给形式参数了表初始化，因此参数的**个数、类型以及顺序**都必须相同
    实参可以传递直接量、变量，表达式以及方法的调用等.


### 常见的访问控制
    public   - 公开的
    protected - 保护的
    默认方式 -默认的
    private - 私有的


​    
#### 访问控制符的比较
    访问控制            访问权限          本类            本包中的其他类         子类          其他包中的其他类
---------------------------------------------------------------------------------------------------------------
       public          公开的            1                   1               1               1
       protected       保护的            1                   1               1
       默认方式          默认的           1                   1                            
       private         私有的            1


​       
a.通常情况下,所有的成员变量都用private修饰，所有额度成员方法都用public修饰
b.public修饰的内容表示可以在任意位置进行访问
c.private修饰的内容只能在本类的内部进行访问
​    
### 包的定义
    package 包名;     //表示创建单层包       
    package 包名1.包名2.....包名n    //表示创建多层包，也就是多层目录，为了管理文件方便，避免文件同名引起冲突

### static关键字    
> 通常情况下成员变量都隶属于对象层级，每个对象都拥有独立的内存空间来记录自己独有的成员变量，当所有的
> 对象的成员变量的值都完全一样时，若每个对象单独记录则会造成内存空间的浪费，此时应该降该成员变量由对象层级提升至
> 类层级，在内存空间中只保留一份且被所有的对象所共享，为了实现该效果，故使用static关键字来修饰，表示静态的含义。
> static关键字可以修饰成员变量和成员方法表示隶属于类层级，推荐使用"类名."的方式访问

- 使用方式
    1.对于非静态的成员方法来说，既可以访问非静态的成员同时也可以访问静态的成员；(成员:成员变量+成员方法)
    2.对于**静态的成员**方法来说，**只能访问静态的成员**，不能访问非静态的成员；(如果非要调用非静态方法，必须使用"对象.非静态方法"的方式访问，对于非静态变量也是如此)
    (执行静态方法的时候**可能还没有创建对象**，非静态成员隶属于对象层级)
    3.只有被所有对象共享的内容才能被static修饰，不能随便加

- 静态成员
    - 存放在JVM的方法区内
    - 使用“类名.”访问
    - 随着类的加载而存在，早于对象的创建
- 非静态成员
    - 存放在JVM的堆内存中    
    - 通过“对象.”访问
    - 随着对象的创建而存在，晚于对象的创建
    
- 注意事项:
    - 静态方法中是无法使用this和super的    

### final关键字(*)
    final本意为最终的，无法更改的，可以修饰类、成员方法和成员变量
    
    final修饰类   最终类       表示该类不能被继承
    final修饰方法 最终方法      表示该方法不能被重写
    final修饰变量 最终变量      

- 使用方式
final关键字修饰类表示该类不能被继承，比如说java.lang.System/String 类等;
    - 通常用于防止滥用继承
final关键字修饰成员方法表示该方法不能被重写;
    - 比如:java.text.SimpleDateFormat类中的format()方法        
    - 通常用于防止不经意间造成的重写
final关键字修饰成员变量表示必须制定初始值并且不能更改
    - 如:java.lang.Thread类中的MAX_PRORITY 
    - 通常用于描述常量的数据
  
    补充:在java语言中很少单独使用static和final关键字，通常使用public static final共同修饰成员变量
    来表示常量的概念，常量的命名规则:所有字母都是大写，不同的单词之间使用_下划线进行连接
    例如:
        public static final double PI=3.14;
        
### 对象创建的过程
#### 单个对象创建的过程
1.将xxx.class文件中的相关类信息读取到内存空间的方法区，这个过程叫做类的加载
2.当程序开始运行时找main()方法去执行方法体重的语句，使用new来创建对象
3.若没有指定初始值，采用默认的初始化，否则采用指定的数值来初始化
4.可以通过构造块来进行更改成员变量的数值
5.执行构造方法体中的语句，可以进行再次的修改成员变量的数值
6.此时对象创建完毕，继续执行后续的语句

TestSuperObject类中的静态语句块
TestSuperObject类中的构造块
TestSuperObject()的方法体

#### 子类对象创建的过程
1.先加载父类再去加载子类，先执行父类的静态语句块，再执行子类的静态语句块；
2.执行父类的构造块，再执行父类的构造方法体，此时父类部分构造完毕
3.执行子类的构造块，再执行子类的构造方法体，此时子类对象构造完毕        

TestSuperObject类中的静态语句块
TestSubObject类中的静态语句块
TestSuperObject类中的构造块
TestSuperObject()的方法体
TestSubObject类中的构造块
TestSubObject()的方法体

总结: **静态块>main()>构造块>构造方法**