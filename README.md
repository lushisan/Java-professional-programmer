# JavaSudy

# day1



+++

#### java的优势

- ##### 跨平台

  - 什么是平台？
    - 指的是操作系统
  - 常见的操作系统？
    - Windows Unix Linux Solaris[Sun]
  - 什么是跨平台？
    - 用java开发出来的应用程序 不受底层操作系统的限制 可以运行在所有的操作系统上面
  - 底层的功臣？
    - JVM = java虚拟机 = 1 + 2 + 3
      - 秘书 + 保镖 + 翻译
      - 秘书 = **类加载器** = ClassLoader
      - 保镖 = **字节码校验器** = ByteCode Verifier
      - 翻译 = **解释执行器 **= Interpreter
      - XXX.java[单词] -》 XXX.class[字节码文件] -》 

- ##### 安全 健壮

  - java的安全性体现在三个方面：

    - 少指针  

    - 多异常[Exception]

    - 多自动的垃圾回收 -》 gc

      - 垃圾：一块不再访问的内存
      - 手动回收垃圾 -》 析构函数

- ##### 免费 开源

- ##### 简单

  - 语法简单：c++--    [取其精华 去其糟粕]

    - 糟粕：指针	运算符重载     手动的垃圾回收

  - 思想简单 = 面向对象的思想 = OO思想

    - 面向**过程**的思想：需要程序员站在计算机的角度去思考问题

    - 面向**对象**的思想：需要拿着代码去模拟现实生活

      - 类：一组类型相同事物高度抽象之后的集合概念
        - 创建对象的模板
        - 类好比工业生产中画的草图
      - 对象：类的一个具体的实例
        - 范冰冰和人之间的关系：对象和类
        - 猫和HelloKitty之间关系：类和对象
        - 对象好比工业生产中 拿着草图生产出来一辆一辆具体的车子
      - 引用：对象的名字    x = new XXX();
        -  在java中每一个对象都需要有名字 一个对象同时可以拥有多个名字 如果一个对象在创建的时候没有名字的话 那么立刻会被gc回收掉 -》 零引用内存回收
      - 属性：对象有什么[一般是名词]
      - 方法：对象会什么[一般是动词]
      - 开发流程：
        - 先写测试类 -》 带有main方法的类
        - 再写实体类 -》 才有属性+方法
          - 定义属性：数据类型 属性名;
          - 定义方法：修饰符 + 返回类型 + 方法名(参数){...}
        - 在main方法测试
          - 创建对象：类名 对象名 = new 类名();
          - 属性赋值：对象名.属性 = 值;
          - 方法调用：对象名.方法名();

- **动态更新**

  - 对于核心类库里面提供的一些方法只保留一个指向的关系 当若干年后 核心类库升级了 我们的程序还是可以继续使用 这是挤兑c/c++的

+++

安装jdk ->  下一步 下一步 下一步......完成

配置环境变量 -> PATH=C:\Program Files\Java\jdk1.8.0_202\bin[我的电脑]

我的电脑 -》 右击 -》 属性 —》 高级 -》 环境变量 -》 PATH -> 编辑 -》 新建 -》 复制 -》 上移到第一个 -》 

3个确定







​      

# day2

**课程内容** 

- 搭建开发环境
- 设置环境变量
- 第一个程序HelloWorld
- java中的软件包结构

+++

#### 搭建开发环境

- 安装jdk[www.oracle.com -> 下载相应的jdk版本]

  - SDK = software development kits = 软件开发工具包[目录/文件夹]
  - JDK = java + SDK = java软件开发工具包  
  - jdk版本：
    - 永久修订版：8  11  17
    - 非永久修订版
  - JRE = java runtime environment = java运行环境 
    - 面试题：jdk和jre之间的区别？
    - jdk表示java软件开发工具包 如果一台电脑上面安装jdk之后 既可以编写代码 又可以运行代码
    - jre表示java运行环境 如果一台电脑上面安装jre之后 只能运行代码

- 设置环境变量

  - ​								给谁使用				作用

  - ##### PATH                 操作系统            让操作系统更加快捷的找到一个文件/命令

    - 为什么需要设置PATH?
    - 当我们在安装jdk的时候 假设装在默认盘符
    - 可是我们的代码可能写在其他的盘符 -》 E:\课件 -》 Test.java
    - 由于计算机看不懂.java文件 所以需要ctrl + 1翻译成.class文件
    - 当我们在按ctrl + 1的时候 底层操作系统开始找javac   
    - 操作系统应该去哪里找javac 看环境变量PATH PATH指向哪里就去哪一个文件夹下面找
    - 所以我们需要设置环境变量 PATH指向jdk下面的bin目录
    - 如果在没有设置PATH的时候 PATH默认指向C:\Windows\System32文件夹          

  - CLASSPATH      类加载器           让类加载器明确去哪里加载.class文件

    - 一般不需要设置 因为他有默认值  默认值：.[当前目录]

  - JAVA_HOME     其他的程序使用的        

+++

#### 第一个程序HelloWorld

- 编译阶段：javac HelloWorld.java
- 运行阶段：java HelloWorld
- 如何在cmd里面编译运行
  - 进入cmd默认在C盘 假设我们的代码写在F:\课件  Test.java
  - 切换盘符 F:回车
  - 进入文件夹  cd 将所在的父目录拖拽进来 回车
  - 编译阶段：javac XXX.java
  - 运行阶段：java XXX

+++

#### java中的软件包结构：

- 包结构 = 操作系统中的文件夹/目录
- 目录[包]的作用？
  - 按照文件的功能 性质进行分类 方便查找....
  - 给出不同的命名规范 从而解决重名的问题    
- 如何打包
  - package 包 背包
  - 必须出现在文件的第一行
- 编译阶段：
  - 以前：javac XXX.java	[没有包结构的代码]
  - 现在：javac **-d** . XXX.java  [带有包结构的代码]
    - **-d**:自动创建包结构
    - **.**:当前文件夹下面创建
- 运行阶段：
  - 以前：java XXX   [不带有包结构]
  - 现在：java 包结构.XXX  [带有包结构]
- 在项目开发的时候 尽量避免包名叫
  - com0-com9:打印机设备
  - con:网络设备
  - nul:空设备

+++

#### java中的数据类型

- 什么是数据类型？

  - 数据类型就是数据的单位 java是一个强类型的编程语言 所有的变量在第一次定义的时候必须有数据类型

- 数据类型分类：

  - 2种/无数种

  - **基本数据类型** 简单数据类型 [程序里面自带的数据类型]

    - 基本数据类型的分类：

    - ###### 布尔类型：boolean   只能使用true[真]/false[假]进行赋值

      - 涉及到判断
        - boolean x = true;
        - boolean y = false;
        - boolean z = 11;//c++可以 但是java语法出错

    - 字符类型：char 底层基于Unicode编码实现的 统一都是2个字节**(2B)** = 16个位**(16bite)**

      - 通常需要描述一个字/一个字母的时候 -》 char

      - ###### char x1 = 'A';//指定字面值的赋值方式

      - ###### char x2 = '男';//指定字面值的赋值方式

      - char x3 = 55;//通过Ascii编码进行赋值

      - char x4 = '\u4e2d';//通过***Unicode编码***进行赋值

      - ###### char x5 = '\t';//转义字符

    - 整数类型：符号位1 + 数值位[n-1]

      - byte           short              int            long[L]

      - 8                16                  32             64

      - 整数类型默认是int类型

      - long类型结尾需要加上L/l 尽量写L

      - 当数值超出int类型最大边界的时候 注意使用long类型

      - 整数类型的赋值方式：

        - ###### int num1 = 55;//十进制赋值

        - int num2 = 055;//八进制赋值

        - int num3 = 0x55;//十六进制赋值

        - int num4 = 0b1100;//二进制赋值

      - byte:-128  127

      - short:-32768  32767

      - int:-2147483648  2147483647

      - long:-XXXXXXXX XXXXXXXX

    - 浮点类型：符号位 + 幂值位 + 数值位

      - float                   double[*]
      - 32                         64
      - F/f                        D/d
      - float : 符号位1 + 幂值位8 + 数值位23
      - double:符号位1 + 幂值位11 + 数值位52
      - 拓展：BigDecimal精度比double类型更高
        - BigDecimal对象.add(BigDecimal对象)
        - BigDecimal对象.subtract(BigDecimal对象)
        - BigDecimal对象.multiply(BigDecimal对象)
        - BigDecimal对象.divide(BigDecimal对象)
        - ***uu.money.add(new BigDecimal("500"))***

  - 基本数据类型之间的转换

    - 小的数据类型可以**自动**变成大的数据类型 [向上转型]
    - 大的数据类型需要**强转**成小的数据类型     [向下转型]
    - short和char之间双向强转
    - byte【-128 127】和char【0-65535】之间双向强转

  - 引用数据类型 自定义数据类型 [程序员自己开发的数据类型]

  

~~~ java
基本数据类型：
  	布尔类型：boolean -> true/false
  	字符类型：char -> 'a'/'中'/'\t'
  	整数类型：byte short int long -> 55
  	浮点类型：float double -> 45.5
  
  	boolean:判断
    char:一个字/字母
    int long:整数
    double BigDecimal[引用数据类型]:小数
~~~



Unicode:  中文  英文 -》 2个字节**(2B)** = 16个位

​	位：计算机底层最小的单位  

ASCII：中文 -》 2个字节		英文 -》 1个字节

​	代码Unicode:    a -> XXXXXXXXXXXXXXXX

   cmd ascii :          a ->XXXXXXXX XXXXXXXX



# day3

课程内容

- 运算符
- java中的变量
- java中的流程控制

+++

#### java中运算符：

- ##### [+ - * / %]

  - +:当+遇到String类型的时候 不再表示算数加法 而是表示***追加连接***
  - *:当心数值超出int类型最大边界 注意使用long类型
  - /:整数/整数 = 整数
    - 7 / 2 = 3
    - 7 / 2.0 = 3.5
  - %:**(取模)**求余数 最终结果的符号位取决于参与运算的第一个数的符号

- ##### [+= -= *= /= %=...]

  - 他们可以保证运算符的左边的数据类型不发生改变 -》 隐式的强转

- ##### [++ --  自增自减运算符]

  - [a:取值	b:运算		x++:ab			++x:ba]

- ##### [>  <  >=  <=  ! =  ==]

  - [> < >= <=]结果都是boolean类型
  - !:非    !boolean      !true = false      !false = true;
  - !=:判断左右两边的值是否不相等
    - System.out.println(45 != 45);//false
  - =和==之间的区别？
    - =：赋值运算符 将右侧的值交给左侧的变量保管   int x = 45;
    - ==:判断左右两边的值是否相等                                 gender == '女'

- ##### && || & |  [逻辑运算符]

  - 面试题：&&和&之间的区别？

    - 相同点：&&和&都是逻辑的与 相当于汉文中并且的意思 需要前后两个条件都成立才能执行
    - 不同点：&&叫做**逻辑的短路与** *<u>有短路特性</u>*
      - 短路特性：如果通过前面的条件可以得出最终结果的话 后面的条件直接舍弃 不在判断
      - 18岁女生     age == 18 && gender == '女'

  - 面试题：||和|之间的区别？

    - 相同点：||和|都是逻辑的或 相当于汉文中或者的意思 需要前后只要有一个条件成立就能执行

    - 不同点：||叫做**逻辑的短路或** <u>*有短路特性*</u>

    - ~~~ java
      boolean		&&		boolean
        true            判断
        false           短路
        
      boolean   ||    boolean
        true            短路
        false           判断
      ~~~

- ##### & | ^ ~ [按位[二进制]运算符]

  - 基本用法：

    ~~~ java
    &:按位的与  上下二进制 都是1才能写1
      	System.out.println(9 & 5);//1
    
    		9=8 + 1 = 000...001001
        5=4 + 1 = 000...000101  &
          			  000...000001 -> 1
         
    |:按位的或 上下二进制 只要有1就写1
      	System.out.println(9 | 5);//13
    		9=8 + 1 = 000...001001
        5=4 + 1 = 000...000101  |
                  000...001101 -> 1 + 4 + 8 = 13
          
    ^:按位的 异或 上下二进制不一样写1
      	9=8 + 1 = 000...001001
        5=4 + 1 = 000...000101   ^
      						000...001100 -> 4 + 8 = 12
      
    ~:按位的 取反 0-》1	1-》0
      	~11101010
         00010101
    ~~~

  - **重点**

    ~~~ java
    &:在某些情况下取代%
      	某些情况 当我们拿着一个正数%上2的n次方数的时候 结果等价于
      	我们拿着这个正数 & 上2的n次方数-1的结果
      	x % 2(n) == x & 2(n)-1
      
      	System.out.println(100 % 8);//100-8-8-8-8-8-8-8-8-8-8-8=4
    		System.out.println(100 & 7);//二进制
    
      27	%2		%4		%8		%16....%2(n)
      		1			3			3			11
      
      27  &1		&3		&7		&15....&2(n)-1
      		1			3			3     11
      
    ^:可以不借助第三块空间的方式交换两个变量的值
      	int x = 45;
    		int y = 90;
    		int z = x;
    		x = y;
    		y = z;
    
    	x = x ^ y;
        y = x ^ y;
        x = x ^ y;
      	
    		能够使用^交换的数据类型：char byte short int long boolean
    ~~~

- [>>  <<  >>> **位** [二进制] **移运算符**]

  ~~~ java
  <<相当于乘以 移动多少位相当于乘以2的几次方数
  >>相当于除以 移动多少位相当于除以2的几次方数
    
  	*2		*4		*8		*16.....*2(n)
    <<1		<<2		<<3		<<4.....<<n
      
    /2		/4		/8		/16..../2(n)
    >>1		>>2		>>3		>>4....>>n
      
   >>和>>>之间的区别？
    	>>叫做 有符号右移 移动之后空缺的高位看原本的符号位
    	01110101 >> 2
    	00011101
    
    	10011111  >> 3
    	11110011
    
    	>>>叫做 无符号右移 移动之后空缺的高位直接补0
    	01110101 >>> 2
      00011101
    
      10011111  >>> 3
      00010011
  ~~~

- **? : [三目运算符  三元运算符]**

  - boolean ? 2 : 3
  - 第一部分为true的话 那么执行第二部分
  - 第一部分为false 的话 那么执行第三部分



~~~ java
+ - * / %
++ --
> < >= <= ! = != ==
&& ||
  
+= -= *= /= %=...
& ^
<< >> 
? :
~~~



+++

#### java中的变量：

- 面试题：java中的**变量**分为几种？
  - **成员变量 实例变量** 属性：定义在类体里面的变量
  - **局部变量  自动变量**：定义在方法体里面的变量
- 面试题：成员变量和局部变量之间的区别？
  - 定义的位置不同
    - 成员变量：定义在**类体**里面
    - 局部变量：定义在**方法**体里面
  - 作用范围不同
    - 成员变量：也叫属性 表示对象有什么 **依赖于对象存在** 当我们new对象的时候 属性也会被创建 当我们回收对象的时候 属性也会被回收
    - 局部变量：从定义的那一行开始 一直到所在的方法体执行结束之前可以访问的 一旦所在的方法体执行结束 局部变量立即消亡 **依赖于方法存在**
  - <u>默认值不同</u>
    - 成员变量：即使不赋值 也有默认值
    - 局部变量：没有默认值的 要求在使用之前必须先赋值
- 成员变量和局部变量<u>可以重名</u>
  - 在重名的时候 如果直接访问这个变量 默认是局部变量
  - 如果想要访问成员变量 需要在变量的前面加上this.

+++

#### java中的流程控制：

- 分支

  - ##### if else

    ~~~ java
    语法格式：
    	if(boolean){
        	执行语句;
      }else if(boolean){
        	执行语句;
      }else if(boolean){
        	执行语句;
      }else{
        	执行语句;
      }
    学会使用if else的排他特性简化代码 不要在下面的条件里面写出上面条件不成立的等价判断
    ~~~

    ##### 拓展：

    plus1:当if else里面只有一个语句的时候 {}可以不写

    plus2:当if里面有return语句的时候 else单词可以不写

    plus3:当if条件为true return true  当if条件为false return false

    ​	其实return回去的就是条件判断而已

    plus4:不要拿着一个boolean类型的变量和true做连等比较

  - ##### switch case

    ~~~ java
    switch:开关		case:情况
      
    语法格式：
     switch(参数){
       case XXX : 执行语句;[break;]
       case YYY : 执行语句;
       case ZZZ : 执行语句;
     } 
    学会使用break共享代码 将执行相同操作的代码放在一起共享
      
    面试题：switch case的参数可以传哪些数据类型？
      	jdk1.0   char byte short int
        jdk5.0   enum[枚举]
        jdk7.0   String
    ~~~






# day4

课程内容

- java中的循环
- 循环控制
- java中的数组

+++

#### java中的循环

- ##### for[控制次数]

  - 语法格式：

    ~~~ java
    for(初始化循环变量;循环执行的条件;循环之后的变化){
      	循环执行的代码;
    }
    ~~~

    

- ##### while[控制条件]

  - 语法格式：

    ~~~ java
    初始化循环变量;
    while(循环执行的条件){
      	循环执行的代码;
      	循环之后的变化
    }
    ~~~

    

- #### do while

  - 语法格式：

    ~~~ java
    赋值;
    do{
      	执行语句;
      	++/--;
    }while(条件);
    
    打印1-100
      int x = 1;
    	while(x <= 100){
        	System.out.println(x);
        	x++;
      }
    
    	int y = 1;
    	do{
        	Ssytem.out.println(y);
        	y++;
      }while(y <= 100);
    ~~~

- ##### 循环控制：

  - 循环嵌套：一个循环定义在另一个循环里面
    - 外层循环一个数字对应整个内层循环
  - 循环控制：
    - **continue****[继续]**:跳过本次循环 跳到所在循环的第三部分
    - **break****[中断]**:跳出所在的循环 跳到所在循环的结束部分
  - 循环标签：
    - 当多个循环嵌套在一起 代码写在最里面循环 处理外层循环的话 需要给外层循环贴标签
    - 然后再内层循环里面continue/break + 标签名

+++

#### java中的数组：

- 什么是数组？
  - **数组：容器 装类型相同 存储空间连续的元素**   
- 数组的基础应用：
  - 创建对象：
    - int[] data = new int[5];
    - int[] data = new int[]{45,66,28,10};
    - int[] data = {34,55,92,10,88};
  - 如何得到某一个元素
    - 数组对象[下标]
  - 如何得到数组大小：
    - 数组对象.length
  - 如何遍历数组
    - for + 下标
      - for(int x = 0;x < data.length;x++){x:下标	data[x]:元素}
    - foreach  forin  since jdk5.0
      - for(数组类型 x : data){}	**[增强for循环]**

+++

#### 数组的复制

- **System.arraycopy(1,2,3,4,5);**
  - 1:要复制的老数组对象
  - 2:老数组的起始下标位置
  - 3:要复制到的目标数组
  - 4:目标数组的起始下标位置
  - 5:要复制的长度
- **Arrays.copyOf(老数组对象,新数组长度);**
  - import java.util.*;

+++

#### 数组的排序

- 手动排序 **冒泡排序**

  ~~~ java
  for(int x = 0;x < data.length -1;x++){//x:控制的是内层循环的次数
    	for(int y = 0;y < data.length -1 -x;y++){//y:控制的元素的下标
        	if(data[y] > data[y + 1]){
            	int z = data[y];
            	data[y] = data[y + 1];
            	data[y + 1] = z;
          }
      }
  }
  
  ~~~

- 自动排序

  - **Arrays.sort(data);**
  - import java.util.*;
  - 只能**升序**排序

+++

#### 引用数据类型的数组

- 当我们创建完一个引用数据类型的数组的时候 其实里面一个元素都没有 里面装的都是null
- 为了防止出现空指针异常 所以在创建完数组之后 一定要给每块空间赋值



# day5

课程内容

- 面向对象
  - 封装
  - 继承
  - 多态
- 方法重载
- 方法覆盖

+++

#### 面向对象的三大特点：封装 继承 多态

#### 面向对象的四大特点：封装 继承 多态 抽象

**封装**：用private将不想被外界访问到的属性/方法隐藏起来

- private:私有的 只有本类可以使用的
- public:公共的 谁都可以使用的
- 封装的好处？
  - 类的开发者：数据得到了保护 从而更加的安全
  - 类的使用者：将精力放在核心业务逻辑上
- 如何封装？
  - 对于属性的封装：每个属性用private修饰 每个属性配套提供两个public修饰的方法 
    - 一个是用来**给属性赋值**的方法 -》 **setter**
    - 一个是用来**获得属性值**的方法 -》 **getter**
  - 对于方法的封装：判断哪些是核心方法
    - 核心方法 -》 public修饰
    - 给核心方法提供服务的方法 -》 private修饰

+++

#### 继承：用extends[派生]实现两个类[子类 父类]之间is a[是一个 是一种]的关系

- 继承是最简单的代码共享方式之一
- java中的类**只能单根继承**
  - class A{}
  - class B{}
  - class C extends A,B{}错误

+++

#### 多态：一个对象有不同的类型去定义它

- 作用一：创建对象  [了解]
  - 父类类型 = new 子类对象()
  - Person x = new Teacher();
  - Animal aa = new Cat();
  - 如果我们使用多态创建一个对象之后 这个对象只能调用子类/父类共有的属性/方法 一旦调用子类特有的属性/方法 报错
- 作用二：放在参数里面用于**解除代码之间的耦合度  [重点]**
  - 耦合度：代码之间的相互依赖程度
  - <u>高内聚 低耦合</u>

+++

#### 方法重载 方法过载 Overload

- 面试题：**方法重载**的条件？

  - 需要发生在<u>同一个类体中</u>

  - <u>方法名需要一摸一样</u>

  - <u>方法的参数需要不同</u>
    - 参数类型不同

    - 参数个数不同

    - 参数顺序不同

- 方法重载的作用？

  ~~~ java
  同时满足用户的不同需求...      
  System.out.println();										println()
  System.out.println(45);									println(int)
  System.out.println(45.5);								println(double)
  System.out.println(1000L);							println(long)
  System.out.println('a');								println(char)
  System.out.println("etoak");						println(String)
  System.out.println(true);								println(boolean)
  ~~~

+++

#### 方法覆盖 方法重写 Override

- **方法覆盖**的条件？

  - 需要发生在**有继承关系的两个类中**  而且是在子类里面发生的
  - 子类在继承得到父类的某些方法之后 觉得父类的实现不好 于是在子类里面重新实现一下

- 方法覆盖注意的知识点：

  ~~~ java
  public void test(int x)throws Exception{}
        |               |
   脑袋        躯干								尾巴
          
  脑袋：访问权限修饰符 >= 父类的权限
       Sun公司认为子类重新实现的方法应该更加优秀 更加优秀的方法应该给更多的人使用 这样才利于java的发展 
         
  躯干：返回类型 + 方法签名			
          	jdk5.0之前	一模一样
            jdk5.0开始 
  尾巴：异常处理部分 <= 父类的异常			范围
       Sun公司认为子类重新实现的方法应该更加优秀 更加优秀的方法不应该有更多的隐患
          
  ~~~

- jdk5.0开始 方法覆盖的时候 可以加上**@Override**

  - **@Override**:注解 用来给机器看的 表示下面的方法一定要覆盖父类的某些方法

- **jdk5.0开始** <u>方法覆盖的时候</u> 其实**返回类型可以改变**了

  - 方法覆盖的时候 返回类型可以变成父类方法返回类型的子类类型 -》 <u>协变返回类型</u>

   

+++

#### 构造方法

- [x] 构造方法是**创建对象的方法**

- [x] 构造方法是创建对象的时候调用的方法 

- 构造方法的作用？

  - 构造方法语法的出现 是为了<u>方便程序员的开发</u>

  - ##### 可以再创建对象的同时 *直接给属性赋值*

  - 在java中只要是个类就一定有构造方法 即使我们没有写系统也会提供一个**默认的构造方法**

  - 默认的构造方法：**无参 空体 没有对属性赋值**

  - 如果我们想要一边创建对象 一边对属性赋值的话 需要自己写一个构造方法

  - 一旦我们写出自己的构造方法之后 ***默认的构造方法将不再提供***

- 构造方法的特点？

  - 没有返回类型 连void都不能写 -》 修饰符 + 方法签名
  - **构造方法的名字需要和类名一模一样** -》 通常首字母大写

- 构造方法的首行:

  - **super()**:要执行本构造方法之前 先去执行父类的构造方法 具体执行父类的哪一个构造方法 看super()里面的参数类型
  - **this()**:要执行本构造方法之前 先去执行本类的其他的构造方法 具体执行本类的哪一个构造方法看参数类型

- 面试题：

  - 构造方法能不能方法<u>重载</u>？
    - **可以**
  - 构造方法能不能方法<u>覆盖</u>？
    - **不可以** **构造方法不能被子类继承**

   

# day6

课程内容

- 扫描仪
- 变量共享
- 方法封装
- 参数传递

+++

#### 扫描仪：Scanner

- Scanner:文本扫描器 用来对用户输入的内容进行扫描
  - 读取字符串：**sc.next() / sc.nextLine()**  /*忽略空格*/
  - 读取数字：**sc.nextInt()**
  - 读取BigDecimal:**sc.nextBigDecimal()**....

+++

#### 参数传递：

- java中只有值传递
- java中基本数据类型**传值** 引用数据类型**传地址**



# day7

课程内容

- String类常见的面试题
- String类常用的20个方法

+++

#### String类型常见的面试题：

- 1：new和不new之间的区别？

  - String x = "OK";
  - String y = new String("OK");
  - 不new的方式涉及到常量池查找机制
  - new的方式 **在堆里面开辟空间** 与此同时在**常量池**里面再次判断有没有

- 2：**String**和**StringBuffer/StringBuilder**之间的区别？

  - String str = new String("OK");
  - StringBuffer buffer = new StringBuffer("OK");
  - StringBuffer和StringBuilder在第一次创建对象的时候 底层会多**预留16块缓冲区**
  - <u>缓冲区为了追加连接效率高</u>

- 3：**StringBuffer**和**StringBuilder**之间的区别？

  - <u>StringBuffer</u>同一时间**允许一个线程**进行访问 效率较**低** 但是**不会**出现**并发错误**

  - <u>StringBuilder</u>同一时间**允许多个线程**进行访问 效率较**高** 但是**可能会**出现**并发错误**

#### String类常见的20个方法

- 和**长度**有关的方法

  | 返回类型 | 方法签名 | 作用                     |
  | :------- | :------- | :----------------------- |
  | int      | length() | 得到一个字符串的字符个数 |

- 和**数组**有关的方法

  | 返回类型 | 方法签名      | 作用                               |
  | :------- | :------------ | :--------------------------------- |
  | byte[]   | getBytes()    | 将一个字符串转换成**字节数组**     |
  | char[]   | toCharArray() | 将一个字符串转换成**字符数组**     |
  | String[] | split(String) | 将一个字符串按照**指定的内容劈开** |

- 和**判断**有关的方法

  | 返回类型 | 方法签名                 | 作用                                                 |
  | :------- | :----------------------- | :--------------------------------------------------- |
  | boolean  | equals(String)           | 判断两个字符串的内容是否一模一样                     |
  | boolean  | equalsIgnoreCase(String) | **忽略大小写**的**比较**两个字符串的内容是否一模一样 |
  | boolean  | contains(String)         | 判断一个字符串里面是否**包含某个内容**               |
  | boolean  | startsWith(String)       | 判断一个字符串是否**以指定的内容开头**               |
  | boolean  | endsWith(String)         | 判断一个字符串是否**以指定的内容结尾**               |

- 和**改变内容**有关的方法 [字符串里面所有的方法都**不会直接的处理原本的字符串** 而是将符合条件的字符串返回给我们 所以注意接收]

  | 返回类型 | 方法签名                    | 作用                                                        |
  | :------- | :-------------------------- | :---------------------------------------------------------- |
  | String   | toUpperCase()               | 将一个字符串全部转换成**大写**                              |
  | String   | toLowerCase()               | 将一个字符串全部转换成**小写**                              |
  | String   | replace(String,String)      | 将字符串里面某个内容**全部替换成指定的内容**                |
  | String   | replaceAll(String,String)   | 将字符串里面某个内容全部替换成指定的内容 **支持正则表达式** |
  | String   | replaceFirst(String,String) | 将字符串里面**第一次出现的某个内容替换**成指定的内容        |
  | String   | trim()                      | **去除**字符串的**前后空格**                                |
  | String   | substring(int x,int y)      | 从下标x一直**截取**到下标y-1对应的元素                      |
  | String   | substring(int x)            | 从下标x一直**截取**到字符串的**最后**                       |

- 和**位置**有关的方法

  | 返回类型 | 方法签名            | 作用                                   |
  | :------- | :------------------ | :------------------------------------- |
  | char     | charAt(int x)       | 找到某个**下标对应**的**元素**         |
  | int      | indexOf(String)     | 找到某个内容**第一次出现**的**下标**   |
  | int      | lastIndexOf(String) | 找到某个内容**最后一次出现**的**下标** |

  

# day8

  课程内容

  - String练习

  - ##### StringBuffer常见的方法

  - 面向对象的高阶特征

    - 访问权限修饰符

    - ##### static修饰符        

    - ##### 单例模式                                                            

    - final修饰符

    - abstract修饰符

+++

  #### 面试题：方法重载和方法覆盖之间的区别？

  - **含义**不同

    ​	方法重载：Overload
    ​	方法覆盖：Override

  - **发生的位置**不同

    ​	方法重载：需要发生在同一个类体中
    ​	方法覆盖：需要发生在有继承关系的两个类中

  - **对参数的要求**不同

    ​	方法重载：参数必须不同[类型 个数 顺序]
    ​	方法覆盖：参数必须相同			

  - **对返回类型的要求**不同

    ​	方法重载：没有要求
    ​	方法覆盖：分版本                       
    ​			jdk5.0之前 一摸一样
    ​			jdk5.0开始 协变返回类型

  - **作用**不同

    - 方法重载：<u>同时满足用户的不同需求</u>

    - 方法覆盖：<u>让一个方法变的更加优秀</u>   				

      	作用不同
      		方法重载：同时满足用户的不同需求
      		方法覆盖：让一个方法变的更加优秀

  #### 面试题：

  - **String**和**StringBuffer/StringBuilder**之间的区别？
    - 创建方式不同
      - String类创建方式：new 不new
      - StringBuffer、StringBuilder创建方式：new  
    - 能不能修改原本的字符串
      - String类里面所有的方法都**不会直接处理**原本的字符串
      - StringBuffer/StringBuilder类里面所有的方法都**可以直接的处理**原本的字符串
    - 有没有缓冲区
      - String类没有缓冲区 单词多长数组空间大小多大
      - StringBuffer/StringBuilder在创建对象的时候 底层会多预留16块缓冲区 追加连接效率高

+++

  #### StringBuffer/StringBuilder类里面常用的方法

  - **append()**:追加连接
  - **reverse()**:反转字符串

+++

  #### 访问权限修饰符：

  - **public**:公共的 谁都可以使用的

  - **protected**:受保护的 只有本包内可以访问 + **包外有继承关系的子类中可以访问**

  - **default**:默认的 只有本包内可以访问

  - **private**:私有的 只有本类可以访问的

  - =====================================================================

  - 各自能修饰哪些东西？

    | 修饰符    | 类   | 成员[属性+方法] |
    | :-------- | :--- | :-------------- |
    | public    | T    | T               |
    | protected | F    | T               |
    | default   | T    | T               |
    | private   | F    | T               |

  - 面试题：

    A类里面定义一个public修饰的方法 在B类里面能用吗？

    不一定 如果B类想要访问A类里面的方法 前提是需要先访问A类

+++

  #### static修饰符：

  - static:静态的 修饰符 相当于汉文中的形容词

  - 面试题：static能修饰什么？

  - **属性**：**静态属性**： 表示整个类型共享一份的属性 不是每个对象都有一份的属性 需要拿着类名去调用

    ​			**普通属性**：表示每个对象都有一份的属性 需要拿着对象去调用

    - **System.out**
    - **System.in**
    - 面试题：java中变量和属性谁大？

      - 变量 
    - static为什么不能修饰局部变量？

      - **static修饰的变量要求类一加载就要在内存里面找到他**  **但是局部变量只有方法调用** 代码执行到那一行的时候才能创建 <u>类的加载永远在前面 方法调用永远在后面</u> 这两个时间点赶不上一起的所以static不能修饰局部变量

  - 方法：静态方法 需要拿着类名去调用

    - 普通方法：需要拿着对象去调用

      

    - 面试题：静态方法和普通方法谁调用简单？

      - 静态方法 

    - 既然静态方法调用简单 开发的时候 为什么不把一个类里面所有的方法都定义成静态的呢？

      - 静态方法里面只能直接的访问静态的成员
      - **普通方法**里面既可以访问**静态成员**也可以访问**非静态成员**
      - **Math.random()**
      - **Arrays.sort()**
      - **System.arraycopy();**
      - **Arrays.copyOf**
      - **System.currentTimeMillis()**

  - 代码块：初始化一个普通属性的

    - 如果我们想要给静态属性赋值的话 需要使用静态代码块
    - 普通代码块：给普通属性赋值的 普通属性每个对象都有一份的属性 每创建一个对象执行一次 创建几个对象执行几次
    - 静态代码块：给静态属性赋值的 静态属性整个类型共享一份 静态代码当类第一次被加载的时候执行 而且只执行一次

+++

  #### 模式：java中本没有模式的概念 用的程序员多了 于是有了模式

  #### 单例模式：控制一个类有且只有一个对象    

  - 醉汉式：
    - 私有化构造方法 防止外界随意的创建对象
    - 创建一个私有的 静态的 属于本类类型的对象
    - 提供一个公共的 静态的 返回本类对象的方法
  - 懒汉式 -》 尚不完善

+++

  #### final修饰符：

  - final 最终的 修饰符 相当于汉文中的形容词

  - 面试题：final能修饰哪些东西？

  - 类：最终类 "骡子类" 

    - 特点：可以有父类 但是**不能有子类**

    - java中的String类和Math类都是最终类

    - String类是比较基础的类 要求所有的程序员使用的都是统一版本

    - Math类里面定义的都是数学里面的公理  定理 不能随意的修改  

      

  - 方法：最终方法

    - 特点：可以被子类继承得到 但是**不能覆盖**

    - Sun公司不在乎我们通过继承得到最终方法 但是需要保证的是这个是最终版本 不能修改

      

  - 变量[属性 + 局部变量]：最终变量 常量

    - 特点：一旦赋值之后 就不能在修改值
    - final double Π = 3.14;

+++

  #### abstract修饰符：

  - **abstract**：抽象的 修饰符 相当于汉文中的形容词
  - 面试题：abstract能修饰哪些东西？
  - 类：抽象类 表示这个类型 **不形象 不具体**
    - 特点：**不能创建对象**
    - 面试题：抽象类是类吗？
      - 是
    - 抽象类有构造方法吗？
      - 有， java中只要是个类就一定有构造方法
    - 抽象类是类 有构造方法 但是不能创建对象 抽象类里面的构造方法作用？
      - 给子类构造方法首行的super()使用的
  - 方法：**抽象方法** 表示这个类型一定会这个方法 **<u>但是现在给不出具体的实现 待留给子类去实现</u>**
    - 一个类里面只要出现了抽象方法 那么这个类一定要变成抽象类
    - 抽象类里面既可以定义抽象方法又可以定义普通方法
  - 面试题：**final**和**abstract**能不能同时修饰一个方法？
    - final修饰的方法 最终方法 可以被继承但是不能被覆盖
    - <u>abstract修饰的方法 抽象方法 **需要子类去覆盖**</u>
    - 矛盾 不能同时修饰一个方法


# day9

课程内容

- java中的接口
- java中的Object类型

+++

#### java中的接口：

- 接口：**interface** 相当于工业生产中的规范

- java中的第二大类型：[他们都可以在编译之后生成.class文件]

  - class				interface				enum				@interface
  - 类                    接口                         枚举                    注解  

- 如何定义接口

  ~~~ java
  interface XXX{
    	接口里面的属性默认加上三个修饰符：public static final
    	int x = 45;
    	接口里面的方法默认加上两个修饰符：public abstract
    	void test();
  }
  ~~~

- 两两之间的关系：

  - <u>类和类</u>：**extends**
  - <u>类和接口</u>：**implements**
  - <u>接口和接口</u>：extends
  - java中的类只能**单根继承**
  - java中的接口允许**多继承 多实现**

- 接口和抽象类<u>不能创建对象</u>

- **方法覆盖**的时候 可以加上**@Override**  //注解，检查

  - 类和类之间的方法覆盖 -》 jdk5.0
  - 类和接口之间的方法覆盖 -》 jdk6.0

- 面试题：抽象类和接口之间的区别？

  - 这是java中的两大类型：
    - **抽象类：class**
    - **接口：interface**
  - 里面定义的属性不同
    - 抽象类：默认都是**普通属性** -》 default String x = "";
    - 接口：默认都是**静态的最终变量** -》 public static final
  - 里面定义的方法不同：
    - 抽象类：**既**可以定义抽象方法**也**可以定义普通方法
    - 接口：里面**只能**定义抽象方法 -》 public abstract
      - **jdk8.0**开始 **接口**里面可以出现**普通方法**了 但是必须加上static/default
      - jdk9.0开始 **接口**里面可以出现**私有方法**了
  - 继承关系不同
    - 抽象类：只能单根继承
    - 接口：允许多继承 多实现

+++

#### Object类型：鼻祖类 所有的类直接父类/间接父类

- clone():"克隆"对象的方法

  - 面试体：深克隆和浅克隆之间的区别？
    - **浅克隆**仅仅克隆一个对象 里面的**属性**还是**共享的状态**
    - **深克隆**将对象克隆 里面的属性也会克隆一份

- ##### toString():制定一个对象打印显示的内容

  - 如果我们想要打印一个引用数据类型的对象的话 那么底层自动拿着<u>**对象.toString()**</u>

  - 如果一个类的toString()**没有覆盖**的话 和**Object类**保持一致

    ~~~ java
    class Object{
      	public String toString(){
          	return getClass().getName() + "@" + 哈希码值的十六进制;
        }
    }
    
    String类继承的得到toString()之后覆盖了toString()
    字符串要求打印对象的时候显示 字符串的内容
    ~~~

- ##### equals():制定一个类型的比较规则 当什么属性一样的话 把他们视为相等对象

  - 如果两个对象想要视为相等对象的话 需要比较equals()

  - equals()在没有覆盖的时候 和Object类保持一致

    ~~~ java
    class Object{
      	public boolean equals(Object obj){
          	return this == obj;//比较地址
        }
    }
    字符串在继承得到equals()方法的时候 方法覆盖 比较字符串的内容
    所以我们自己写的类在没有覆盖equals()方法的时候比较地址
    ~~~

  - 面试题：**==** 和 **equals()** 之间的区别？

    - ==是一个运算符 判断左右两边的值是否相等
      - <u>基本数据类型</u>：**比较数值**
      - <u>引用数据类型</u>：**比较地址**
    - **equals()**:判断两个对象能不能视为相等对象 程序员可以按照自己的意愿 将内存里面不同的两个对象视为相等对象 只能引用数据类型

- ##### hashCode():得到一个对象的<u>散列特征码</u>

  - 散列：将一大组数据分散为不同的小组
  - 注意：当此**方法[equals]**被重写时，通常有必要**重写 hashCode 方法**，以维护 hashCode 方法的常规协定，该协定声明相等对象必须具有相等的哈希码。
  - x.equals(y) == true
  - x.hashCode() == y.hashCode()















  

  



​    

  



​      

​      

​      

​      

