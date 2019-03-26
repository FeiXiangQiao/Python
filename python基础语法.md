
## 一、Python基础语法  
1. 注释：#标注的文本  
2. 数字  
    * 整数  
        &ensp;&ensp;&ensp;&ensp;python3开始不区分long和int，long被重命名为int，所有只有int  
        &ensp;&ensp;&ensp;&ensp;进制0xa、0o10、0b10  
        &ensp;&ensp;&ensp;&ensp;bool， 2个值True、False  
    * 浮点数  
        &ensp;&ensp;&ensp;&ensp;1.2、3.1415、-0.12,1.46e9等价于1.46\*10³\*10³
        &ensp;&ensp;&ensp;&ensp;本质上使用了C语言的double类型  
    * 复数，1+2j  
3. 字符串  
    &ensp;&ensp;&ensp;&ensp;使用'"单双引号引用的字符的序列  
    &ensp;&ensp;&ensp;&ensp;'''和"""单双三引号，可以跨行，可以其中自由的使用单双引号  
    &ensp;&ensp;&ensp;&ensp;r前缀：在字符串前面加上r或者R前缀，表示该字符串不做特殊的处理  
    &ensp;&ensp;&ensp;&ensp;f前缀：3.6版本开始，新增f前缀，格式化字符串  
4. 转义序列  
    &ensp;&ensp;&ensp;&ensp;\\ \t \r \n \' \"  
    &ensp;&ensp;&ensp;&ensp;前缀r,把里面的所有字符当普通字符对待  
5. 缩进  
    &ensp;&ensp;&ensp;&ensp;未使用C等语言的花括号，而是采用缩进的方式表示层次关系  
    &ensp;&ensp;&ensp;&ensp;约定使用4个空格缩进  
6. 续行  
    &ensp;&ensp;&ensp;&ensp;在行尾使用\  
    &ensp;&ensp;&ensp;&ensp;如果使用各种括号，认为括号内是一个整体，内部跨行不用\  
7. 标识符  
    &ensp;&ensp;&ensp;&ensp;1、一个名字，用来指代一个值  
    &ensp;&ensp;&ensp;&ensp;2、只能是字母、下划线和数字  
    &ensp;&ensp;&ensp;&ensp;3、只能以字母或下划线开头  
    &ensp;&ensp;&ensp;&ensp;4、不能是python的关键字，例如def、class就不能作为标识符  
    &ensp;&ensp;&ensp;&ensp;5、python是大小写敏感的  
    &ensp;&ensp;&ensp;&ensp;约定：  
    &ensp;&ensp;&ensp;&ensp;不允许使用中文  
    &ensp;&ensp;&ensp;&ensp;不要使用歧义单词，例如class_  
    &ensp;&ensp;&ensp;&ensp;在python中不用随便使用下划线开头的标识符  
8. 常量  
    &ensp;&ensp;&ensp;&ensp;一旦赋值就不能改变值的标识符  
    &ensp;&ensp;&ensp;&ensp;python中无法定义常量  
9. 字面常量  
    &ensp;&ensp;&ensp;&ensp;一个单独的量，例如12、"abc"、'2341356514.03e-9'  
10. 变量  
    &ensp;&ensp;&ensp;&ensp;赋值后，可以改变值的标识符  
  
## 二、Python的语言类型  
* Python是动态语言、强类型语言  
* 静态编译语言  
    &ensp;&ensp;&ensp;&ensp;实现声明变量类型，类型不能再改变  
    &ensp;&ensp;&ensp;&ensp;编译时检查  
* 动态编译语言  
    &ensp;&ensp;&ensp;&ensp;不用事先声明类型。随时可以赋值为其他类型  
    &ensp;&ensp;&ensp;&ensp;编程时不知道是什么类型，很难推断  
* 强类型语言  
    &ensp;&ensp;&ensp;&ensp;不用类型之间操作，必须先强制类型转换为同一类型。print('a'+1)  
* 弱类型语言  
    &ensp;&ensp;&ensp;&ensp;不同类型间可以操作，自动隐式转换，Javascript中console.log(1+'a')  
    ![语言类型比较](https://img-blog.csdnimg.cn/20190326160815634.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZlaXhpYW5ncWlhbw==,size_16,color_FFFFFF,t_70)
  
## 三、Python的进制  
* 常见进制有二进制、八进制、十进制、十六进制。重点掌握二进制、十六进制  
    >十进制逢十进一；十六进制逢十六进一；二进制逢二进一  
* 转为十进制----按位乘以权累加求和  
    &ensp;&ensp;&ensp;&ensp;0b1110计算为1 \* 2 \*\* 3 + 1 \* 2 \*\* 2 + 1 \* 2 \*\* 1 + 0 \* 2 \*\* 0 = 14  
    &ensp;&ensp;&ensp;&ensp;0x41计算为4 \* 16 + 1 \* 1 = 65  
* 转为二进制  
    &ensp;&ensp;&ensp;&ensp;0xF8按位展开即可，得到 0b1111 1000  
    &ensp;&ensp;&ensp;&ensp;127除以基数2，直到商为0为止，反向提取余数  
* 转为十六进制  
    &ensp;&ensp;&ensp;&ensp;127除以基数16，直到商为0为止，反向提取余数  
    ![十六进制](https://img-blog.csdnimg.cn/20190326161100826.png)![二进制](https://img-blog.csdnimg.cn/20190326161046650.png)
## 四、Python运算符Operator  
1. 算数运算符  
    &ensp;&ensp;&ensp;&ensp;+ - * / % **  
    &ensp;&ensp;&ensp;&ensp;自然除/结果是浮点数，整除//。注：2.x中/和//都是整除  
    * &ensp;&ensp;&ensp;&ensp;%解释：  
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;格式为:a%b=c  
       &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;取模运算，结果的符号由第二个操作数b的符号决定,取模运算在计算c的值时，向负无穷方向舍入。   
       &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;1) 整数取模的数学定义:当a和b中存在负整数时，首先计算|a|%|b|=c，然后a%b的符号与b一致。也就是说，如果b>0，则a%b=c；如果b<0，则a%b=-c  
       &ensp;&ensp;&ensp;&ensp;例如：  
       &ensp;&ensp;&ensp;&ensp;整数中，当a>b时
    ```python
        In [2]: 5 % 2
        Out[2]: 1

        In [3]: -5 % 2
        Out[3]: 1

        In [4]: 5 % -2
        Out[4]: -1

        In [5]: -5 % -2
        Out[5]: -1
    ```
     &ensp;&ensp;&ensp;&ensp;解释:  
    ```python
     5/2=2.5则5%2=5-(2*2)=1  
     -5/2=-2.5则-5%2=-5-(-3*2)=1  
     5/-2=-2.5则5%-2=5-(-3*-2)=-1  
     -5/-2=2.5则-5%-2=-5-(2*-2)=-1  
    ```

    &ensp;&ensp;&ensp;&ensp;整数中，当a<b时

    ```python
        In [7]: 2 % 3
        Out[7]: 2

        In [8]: -2 % 3
        Out[8]: 1

        In [9]: 2 % -3
        Out[9]: -1

        In [10]: -2 % -3
        Out[10]: -2
    ```
    &ensp;&ensp;&ensp;&ensp;解释:   
    ```python
    2/3=0.6则2%3=2-(0*3)=2
    -2/3=-0.6则-2%3=-2-(-1*3)=1
    2/-3=-0.6则2%-3=2-(-1*-3)=-1
    -2/-3=0.6则-2%-3=-2-(0*-3)=-2
    ```

    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;2)浮点数取模的数学定义：对于两个浮点数a和b，a % b = a - n * b，其中n为不超过a / b的最大整数。  
    浮点数中，当a<b时
    ```python
        In [18]: 1.5%2.5
        Out[18]: 1.5

        In [19]: 1.5%-2.5
        Out[19]: -1.0

        In [20]: -1.5%2.5
        Out[20]: 1.0

        In [21]: -1.5%-2.5
        Out[21]: -1.5
    ```
    &ensp;&ensp;&ensp;&ensp;解释: 
    ```python
    1.5/2.5=0.6则1.5%2.5=1.5-(0*2.5)=1.5
    1.5/-2.5=-0.6则1.5%-2.5=1.5-(-1*-2.5)=-1.0
    -1.5/2.5=-0.6则-1.5%2.5=-1.5-(-1*2.5)=1.0
    -1.5/-2.5=0.6则-1.5%-2.5=-1.5-(0*-2.5)=-1.5
    ```
    &ensp;&ensp;&ensp;&ensp;浮点数中，当a>b时
    ```python
    In [22]: 3.5%2.5
    Out[22]: 1.0

    In [23]: 3.5%-2.5
    Out[23]: -1.5

    In [24]: -3.5%2.5
    Out[24]: 1.5

    In [25]: -3.5%-2.5
    Out[25]: -1.0
    ```
    &ensp;&ensp;&ensp;&ensp;解释: 
    ```python
    3.5/2.5=1.4则3.5%2.5=3.5-(1*2.5)=1.0
    3.5/-2.5=-1.4则3.5%-2.5=3.5-(-2*-2.5)=-1.5
    -3.5/2.5=-1.4则-3.5%2.5=-3.5-(-2*2.5)=1.5
    -3.5/-2.5=1.4则-3.5%-2.5=-3.5-(1*-2.5)=-1.0
    ```
2. 位运算符  
    & | ~ ^ << >>  
    * &:  
    &ensp;&ensp;&ensp;&ensp;按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0  
    &ensp;&ensp;&ensp;&ensp;例如:
        ```python
        9&8 = 8
        0000 1001  & 0000 1000 = 0000 1000
        In [26]: 9&8
        Out[26]: 8
        ```
    * |:  
    &ensp;&ensp;&ensp;&ensp;按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1
        ```python
        9&8 = 9
        0000 1001  & 0000 1000 = 0000 1001
        In [26]: 9|8
        Out[26]: 9
        ```
    * ~:  
    &ensp;&ensp;&ensp;&ensp;按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1 。~x 类似于 -x-1  
    &ensp;&ensp;&ensp;&ensp;12, 0xc, 0o14, 0b1100  
    &ensp;&ensp;&ensp;&ensp;~12等于多少，为什么  
        ```python
        ~12
        In [32]: ~12
        Out[32]: -13
        0000 1100得出反码位为1111 0011，然后根据原码有效位得出补码位为1000 1101，负数最高加1，  
        得出最高位为1000,其余位不变取反后+1，得出1101，最后结果为1000 1101
        ```
    >原码、反码、补码，负数表示法  
    原码  
        5=> 0b101, 1=> 0b1, -1 => -0b1, bin(-1)  
    反码  
        正数的反码与原码相同；负数的反码符号位不变其余按位取反  
    补码  
        正数的补码与原码相同；负数的补码符号位不变其余按位取反后+1  
    负数表示法  
        早期数字电路的cpu中的运算器实现了加法器，但是没有减法器，减法要转换成加法  
        负数在计算机中使用补码存储，-1的补码为1111 1111  
        5-1=> 5+(-1)直觉上是0b101-0b1，其实计算机中是0b101 + 0b11111111，溢出位舍弃   
    * ^:  
    &ensp;&ensp;&ensp;&ensp;按位异或运算符：当两对应的二进位相异时，结果为1  
        ```python
        9^8 = 1
        0000 1001  ^ 0000 1000 = 0000 0001
        In [29]: 9^8
        Out[29]: 1
        ```
    * <<:  
    &ensp;&ensp;&ensp;&ensp;左移动运算符：运算数的各二进位全部左移若干位，由 << 右边的数字指定了移动的位数，高位丢弃，低位补0。
        ```python
        9<<3 = 72
        0000 1001 = 0100 1000
        In [30]: 9<<3
        Out[30]: 72
        ```
    * \>>:  
    &ensp;&ensp;&ensp;&ensp;右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，>> 右边的数字指定了移动的位数
    常用方式：乘除2的倍数，32//8相当于32 >> 3 
        ```python
        9>>2 = 2
        0000 1001  = 0000 0010
        In [31]: 9>>2
        Out[31]: 2
        ```
3. 比较运算符  
    &ensp;&ensp;&ensp;&ensp;== != > < >= <=  
    &ensp;&ensp;&ensp;&ensp;返回一个bool值  
    &ensp;&ensp;&ensp;&ensp;1<'1' 1=='1'  
    &ensp;&ensp;&ensp;&ensp;链式比较操作符  
        &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;4>3>2     4>mynumber>=1  
4. 逻辑运算符  
    * 与或非 and or not  
    * 短路运算符  
        &ensp;&ensp;&ensp;&ensp;and如果第一个表示式为False，后面就没有必要计算了，这个逻辑表达式一定是False  
        &ensp;&ensp;&ensp;&ensp;or如果第一个表示式True，后面没有必要计算了，这个逻辑表达式一定是True  
5. 赋值运算符  
    &ensp;&ensp;&ensp;&ensp;a = min(3,5)  
    &ensp;&ensp;&ensp;&ensp;+= -= *= /= %=等  
    &ensp;&ensp;&ensp;&ensp;x = y = z = 10  
6. 成员运算符  
    &ensp;&ensp;&ensp;&ensp;in、not in  
7. 身份运算符  
    &ensp;&ensp;&ensp;&ensp;is、is not  
8. 运算符优先级(由高到低)  
    |运算符     |描述        |  
    |:--------:|:----------:|  
    |'expr'|字符串转换|  
    |{key:expr,....}|字典|  
    |[expr1,expr2....]|列表|  
    |(expr1,expr2....)|元组|  
    |function(expr1,....)|函数调用|  
    |x[index:index]|切片|  
    |x[index]|下标索引取值|  
    |x.attribute|属性引用|  
    |~x|按位取反|  
    |+x, -x|正, 负|  
    |x**y|幂|  
    |x*y, x/y, x%y|乘, 除, 取模|  
    |x+y, x-y|加，减|  
    |x<<y, x>>y|移位|  
    |x&y|移位与|  
    |x^y|按位异或|  
    |x|y|按位或|  
    |x<y, x<=y, x==y, x!=y, x>=y, x>y|比较|  
    |x is y, x is not y|等同测试|  
    |x in y, x not in y|成员判断|  
    |not x|逻辑否|  
    |x and y|逻辑与|  
    |x or y|逻辑或|  
    |lambda arg,....:expr|Lambda匿名函数|  
  
    >算法运算符 > 位运算符 > 身份运算符 > 成员运算符 > 逻辑运算符  
    单目 > 双目  
    记不住，用括号  
    长表达式，多用括号，易懂、易读  
## 五、表达式Expression  
* 由数字、符号、括号、变量等的组合  
    &ensp;&ensp;&ensp;&ensp;算法表达式  
    &ensp;&ensp;&ensp;&ensp;逻辑表达式  
    &ensp;&ensp;&ensp;&ensp;赋值表达式  
        &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;Python中，赋值即定义，如果一个变量以及定义，赋值相当于重新定义  
  
## 六、内存管理    
1. 变量无须事先声明。也不需要指定类型，这是动态语言的特性  
2. Python编程中一般无须关心变量的存亡，一般也不关心内存的管理  
3. Python使用引用计数记录所有对象的引用数  
    * 当对象引用数变为0，它就可以被垃圾回收GC  
    * 计数增加：  
        &ensp;&ensp;&ensp;&ensp;赋值给其它变量就增加引用计数，例如x=3;y=x;z=[x,1]  
        &ensp;&ensp;&ensp;&ensp;实参传参，如foo(y)  
    * 计数减少：  
        &ensp;&ensp;&ensp;&ensp;函数运行结束时，局部变量就会被自动销毁，对象引用计数减少  
        &ensp;&ensp;&ensp;&ensp;变量被赋值给其他对象。例如x=3;y=x;x=4  
4. 有关注性能的时候，就需要考虑变量的引用问题，但是该释放内存还是尽量不释放内存，看需求  
5. 查看引用计数  
    ```python  
    In [54]: import sys
        ...: a=['lllll']
        ...: b=a
        ...: c=b
        ...:
        ...: print(sys.getrefcount(a))
    4
    ```
## 七、if语句  
### 1、真值表  
|对象/常量|值|  
|:--------:|:--------:|  
|""|假|  
|"string"|真|  
|()|假|  
|>=1|真|  
|<=-1|真|  
|()空元组|假|  
|[]空列表|假|  
|{}空字典|假|  
|None|假|  
  
* False等价布尔值，相当于bool(value)  
    1)空容器  
        &ensp;&ensp;&ensp;&ensp;空集合set  
        &ensp;&ensp;&ensp;&ensp;空字典dict  
        &ensp;&ensp;&ensp;&ensp;空列表list  
        &ensp;&ensp;&ensp;&ensp;空元组tuple  
    2)空字符串  
    3)None对象  
    4)0  
  
### 2、单分支结构  
* if语句  
    ```python
    if condition:  
        代码块  
    condition必须是一个bool类型,这个地方有一个隐式转换bool(condition)  
    if 1<2: #if True:  
        print('1 less than 2') 
    ```
* 代码块  
    &ensp;&ensp;&ensp;&ensp;类似于if语句的冒号后面的就是一个语句块  
    &ensp;&ensp;&ensp;&ensp;在if、for、def、class等关键字后使用代码块  
  
### 3、多分支结构  
```python
if...elif...else语句  
    if condition1:  
        代码块1  
    elif condition2:  
        代码块2  
    elif condition3:  
        代码块3  
    ......  
    else:  
        代码块  
```
### 4、分支嵌套  
* 嵌套结构，可以是分支、循环的嵌套  
* 可以互相嵌套多层  
* 多分支结构，只要有一个分支被执行，其他分支都不会被执行  
* 前一个条件被测试过，下一个条件相当于隐含着这个条件  
举例：  
  
### 5、练习题：  
* 输入2个数字，输出最大数  
  ```python
    num = int(input("Please input number:"))

    if num <= 80:
        print('very good')
    elif num < 60:
        print('good')
    else:
        print('not good')
  ```
* 给定一个不超过5位的正整数，判断其有几位  
  ```python
    x=int(input("Please input number:"))
    if x >= 1000:
        if x >= 10000:
            print("x >= 10000")
        else:
            print("x >= 1000")
    elif x >= 10:
        if x >= 100:
            print("x >= 100")
        else:
            print("x >= 10")
    else:
        print("x < 10")
  ```
* 使用input函数  
    input函数获取键盘输入input([prompt])，返回一个输入的字符串
    ```python
    In [59]: input("Please input number:")
    Please input number:100
    Out[59]: '100'
    ```
* int函数  
    把给定类型的数值转换为整数  
    ```python
    In [60]: num='100'

    In [61]: type(num)
    Out[61]: str

    In [62]: num1=int(num)
    In [63]: num1
    Out[63]: 100

    In [64]: type(num1)
    Out[64]: int
    ```