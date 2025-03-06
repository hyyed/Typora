# TCL语法基础

## **脚本学习核心**

• TCL脚本执行依赖于**解释器**（逐行执行）。
• **TCL有效命令行**以命令+字符串（**结合空格间隔符**）形成
• 明白置换（**$、［］、\**）和引用（**''",｛｝**）的差别和联系。
• 理解命令**expr、source、eval、exec**的差别。
• 掌握**｛\*｝配合glob等返回list后**的操作

> $ ：置换为他的值
>
> [] ：包裹一行中第二个命令
>
> "" ：保证整体性
>
> {} ：
>
> () ：数组的索引
>
> [expr]：命令置换
>
> \ ：反斜杠置换



## **基础语法**

• 一个**TCL脚本**可以包含**一个或多个命令**。命令之间必须用换行符或分号隔开，下面的两个脚本都是合法的：

```TCL
set a 1
set b 2
或set a 1; set b 2
puts "aaa"	#输出: aaa
```

• **TCL每一命令**包含**一个或几个单词**，第一个单词代表***\*命令名\****,**另外的单词**则是这个命令的参数，单词之间必须用**空格或TAB键隔开**。

•注释：使用#注释，**set foo 0**； #注释内容，**注释符号前应该有分号，**因为tcl解析器总是认为一条命令应该以换行或者分号结束，其他的在同一行中都认为是参数。

### 特殊变量

| r.No. |  |                        特殊变量&说明                         |
| ---- | ---- | ---- |
| 1     | argc |                  指许多命令行参数.                   |
| 2     | argv |              参考包含的列表命令行参数.               |
| 3     | argv0 |    指正在解释的文件的文件名或我们调用脚本的名称.    |
| 4     | env  |            用于表示作为环境变量的元素数组.            |
| 5     | errorCode |          提供错误代码最后一个Tcl错误.           |
| 6     | errorInfo |           提供上次Tcl错误的堆栈跟踪.            |
| 7     | tcl_interactive | 用于通过将此设置分别设置为1和0来在交互模式和非交互模式之间切换. |
| 8     | tcl_library |           用于设置标准Tcl库的位置.            |
| 9     | tcl_pkgPath |           提供清单通常安装包的目录.           |
| 10    | tcl_patchLevel |         指Tcl解释器的当前补丁级别.         |
| 11    | tcl_platform | 用于表示包含byteOrder，machine，osVersion，platform和os等对象的元素数组. |
| 12    | tcl_precision | 指精度即数字o转换为浮点数到字符串时保留的f个数字.默认值为12. |
| 13    | tcl_prompt1 |                  指主要提示.                  |
| 14    | tcl_prompt2 |          引用带有无效命令的辅助提示.          |
| 15    | tcl_rcFileName |          提供用户特定的启动文件.           |
| 16    | tcl_traceCompile | 用于控制字节码编译的跟踪.使用0表示无输出，1表示摘要，2表示详细信息. |
| 17    | tcl_traceExec | 用于控制字节码执行的跟踪.使用0表示无输出，1表示摘要，2表示详细信息. |
| 18    | tcl_version |           返回当前版本的Tcl解释器.            |

### 保留字

以下列表显示了Tcl中的一些保留字.这些保留字不能用作常量或变量或任何其他标识符名称.

| after       | append     | array           | auto_execok  |
| ----------- | ---------- | --------------- | ------------ |
| auto_import | auto_load  | auto_load_index | auto_qualify |
| binary      | Bgerror    | break           | catch        |
| cd          | Clock      | close           | concat       |
| continue    | Dde        | default         | else         |
| elseif      | Encoding   | eof             | error        |
| eval        | Exec       | exit            | expr         |
| fblocked    | Fconfigure | fcopy           | file         |
| fileevent   | Flush      | for             | foreach      |
| format      | Gets       | glob            | global       |
| history     | If         | info            | interp       |
| join        | Lappend    | lindex          | linsert      |
| list        | Llength    | load            | lrange       |
| lreplace    | Lsearch    | lsort           | namespace    |
| open        | Package    | pid             | pkg_mkIndex  |
| proc        | Puts       | pwd             | read         |
| regexp      | Regsub     | rename          | resource     |
| return      | Scan       | seek            | set          |
| socket      | Source     | split           | string       |
| subst       | Switch     | tclLog          | tell         |
| time        | Trace      | unknown         | unset        |
| update      | Uplevel    | upvar           | variable     |
| vwait       | While      |                 |              |

## **置换(substitution )**

• TCL解释器在分析命令时，把**所有的命令参数都当作字符串**看待，数据类型：tcl不支持其他语言中的形如int, double ,char等等类型，唯一支持的就是string类型。例如:

```tcl
set x 10;        #定义变量x,并把x的值赋为10
10
set y x+100;	#y的值是x+100,而不是我们期望的110
x+100
```

上例的第二个命令中，x被看作字符串x+100的一部分，如果我们想使用x的值'10',就必须告诉TCL解释器：我们在这里**期望的是变量x的值，而非字符'X'**，怎么告诉TCL解释器呢，这就要用到TCL语言中提供的置换功能。
• TCL提供三种形式的置换：变量置换、命令置换和反斜杠置换.

### 变量置换 \$

•变量置换由一个**$符号**标记，**变量置换会导致变量的值插入一个单词中**。例如：

```tcl
set y $x+100; 	#y的值是10+100,这里x被置换成它的值10
10+100			#y的值还不是我们想要的值110,而是10+100,因为TCL解释器把10+100看成是一个字符串而不是表达式
```


要想得到值110,还必须用命令置换，使得TCL会把10+100看成一个**表达式并求值**。

### 命令置换 [expr ]

•命令置换是由 **[ ] 括起来**的TCL命令及其参数，**命令置换**会导致**某一个命令的所有或部分单词被另一个命令的结果所代替**。例如：

```tcl
set y [expr $x + 100];	#TCL解释器遇到字符'['时，它就会把随后的 expr 作为一个命令名
110						#某一个命令的所有或部分单词被另一个命令的结果所代替

set variableA "10"
set tcl_precision 5;	#保留五位有效数字
set result [expr $variableA / 9.0];
puts $result
1.1111
```

• y的值是110 , 这里当**TCL解释器遇到字符'['时**，它就会把随后的**expr**作为一个命令名，从而激活与expr对应的C/C++过 程，**并把'expr'和\**变量置换\**后得到的'10+110' 传递给该命令过程进行处理**。

• 如果在上例中我们去掉 [ ]，那么TCL会报错 。因为在正常情况下 ,**TCL解释器只把命令行中的第一个单词作为看作命令，其他的单词都作为普通字符串处理，看作是命令的参数**。

### 反斜杠置换 \\

| string  | 说明         | 十六进制值                                                |
| ------- | ------------ | --------------------------------------------------------- |
| \A      | 声音铃声     | 0x07                                                      |
| \b      | 退格键       | 0x08                                                      |
| \F      | 换页（清屏） | 0x0c                                                      |
| \n      | 新行         | 0x0a                                                      |
| \r      | 回车         | 0x0d                                                      |
| \t      | 水平标签     | 0x09                                                      |
| \v      | 垂直制表符   | 0x0b                                                      |
| \0dd    | 八进制值     | d 是 0-7 之间的数字                                       |
| \uHHHH  | H            | 是十六进制数字 0-9,AF,af。这代表一个 16 位 Unicode 字符。 |
| \xHH... | 十六进制值   | H 是十六进制数字 0-9,AF,af。                              |
| \?      | ?字符        |                                                           |
| \'      |              |                                                           |

- 请注意，只要 \x 具有十六进制数字，\x 替换就会“继续进行”，并且仅使用最后两个，这意味着 \xaa 和 \xaaaa 相等，并且 \xaaAnd 无论如何都会“吃掉”“And”的 A 。使用 \u 表示法可能是一个更好的主意。

• TCL语言中的**反斜杠\置换**似于C语言中反斜杠的用法，主要用于**在单词符号中插入诸如 换行符、空格、［、$**等被TCL解释器当作**特殊符号**对待的字符。例如：

```tcl
set msg mult\niplex\ space;         #如果没有 '\' 的话，TCL会报错，因为解释器会把这里最后两个单词之间的空格认为是分隔符，
								#于是发现set命令有多于两个参数,从而报错
mult
iple space
```

•如果没有 '\\' 的话，TCL会报错，因为**解释器会把这里最后两个单词之间的空格认为是分隔符，于是发现set命令有**多于两个参数,从而报错。加入了'\‘后，空格不被当作分隔符，'multiple space‘被认为是一个单词(word)。

![img](https://gitee.com/jiagnkun/procotol_device/raw/master/Typora/DaLei/assic.picture/202307301929869.png)

```tcl
set a \x48 ;    #对应 \xhh
H                   #十六进制的48是72,对应字符H
```

### 双引号和花括号

• 除了使用**反斜杠**外，TCL提供另外两种方法来使得解释器**把分隔符和置换符等特殊字符当作普通字符，而不作特殊处理**，这就要使用双引号" "和花括号({})。
• TCL解释器**对双引号中的各种分隔符将不作处理**，但是对**换行符及$和[ ]**两种置换符会照常处理。

```tcl
set y "$x ddd";	#对双引号中的各种分隔符将不作处理，但是对 换行符及$和[ ] 两种置换符会照常处理
100 ddd

set "aaa bbb"
aaa bbb
```

## 变量

### 简单变量

 一个TCL简单变量包含两个部分 ：名字和值。**名字和值**都可以是**任意字符串**。
TCL解释器在分析一个**变量置换**时，只把从$符号往后直到**第一个**不是字母、数字或下划践的字符之间的单词符号作为要被置换的变量的名字。**变量：在tcl变量不需要声明就可以直接赋值**,

```tcl
set a 2 ;   set a.1 4;   set b $a.1;
a = 2         a.1 = 4         b = 2.1#2.1是一个字符串
```


• 在最后—命令行，我们希望把**变量a.1的值付给b**,但是TCL解释器在分析时**只把$符号之后直到第一个不是字母、数字或下划线的字符**(这里是之间的单词符号(这里是'a')当作要被置换的变量的名字，所以TCL解释器把a置换成2,然后把字符串付给变量b。这显然与我们的初衷不同。

•如果变量名中有**不是字母、数字或下划线的字符**，又要用**置换**,可以用**花括号**把变量名括起来。

```tcl
set b ${a.1}；
4
```

**变量读取**
•TCL中的set命令能生成一个变量、也能读取或改变一个变量的值

```tcl
set a {kdfj kjdf} ;   # 变量a的值是kdfj kjdf   
set a;
kdfj kjdf
```

### 局部变量与全局变量

`global`是一个关键字，用于在过程内部访问全局变量。它的作用是将一个或多个全局变量引入到当前过程的作用域，使得过程可以读取或修改这些全局变量的值。

当在一个过程内部需要访问全局变量时，如果不使用`global`关键字，Tcl会将变量视为局部变量，即使全局变量与局部变量的名称相同，也会被视为不同的变量。使用`global`关键字可以明确指示变量是全局变量，从而正确地访问全局范围内的变量。

```tcl
set a 4                      ;# 先置全局变量a为4
proc sample { x } {          ;# 创建程序
	global a				;# 访问全局变量 a
	incr a
	return [expr $a+$x])
}
sample 3                      ;# x=3，返回结果8
set a                         ;# 获取变量a的值是5
```


•如果我们想在过程内部引用一个全局变量的值，可以使用global命令
•**全局变量a在过程中被访问**。在过程中对a的改变会直接反映到全局上。如果去掉语句global a, TCL会出错，因为它不认识变量a。
• 对于在过程中定义的变量 ， 因为它们只能在过程中被访问，并且当过程退出时会被自动删除，所以为***\*局部变量\****；在所有过程之外定义的变量称之为**全局变量**。
• TCL中 ， 局部变量和全局变量可以同名 ，两者的**作用域交集为空**：局部变量的作用域是它所在的过程的内部：**全局变量的作用域则不包括所有过程的内部**。这一点和C语言有很大的不同.



### 数组

•数组是一些**元素**的集合。TCL数组和普通计算机语言中的数组有很大的区别。在TCL中，**不能单独声明一个数组，\**数组\**只能和\**数组元素\**一起声明**。数组中，数组元素的名字包含两部分：***\*数组名和数组中元素的名字\****，TCL中数组元素的名字(下标)可以为任何字符串。

```tcl
set day(monday) 1; 	#生成一个名为 day 的数组 ， 同时在数组中生成 一个名为monday的数组元素，并把值置为1
set day(tuesday) 2;	#生成一个名为tuesday的数组元素，并把值置为2
```

## 相关命令

### source

```tcl
# source 命令读一文件并把这个文件的内容作为一个脚本进行求值
source e:/tcl&c/hello.tcl		;# 读一文件并把这个文件的内容作为一个脚本进行求值
source c:/tcl_file/test_tcl.tcl	;# vivado中调用 tcl文件
```

### eval

 eval命令是一个用来构造和执行TCL脚本的命令

```tcl
语法： eval arg arg ...   
#它可以接收一个或多个参数，然后把所有的参数以空格隔开组合到一起 成为一个脚本，然后对这个脚本进行求值。
 eval set a 2 ;set b 4	;# 4
 set cmd "expr $a + $b"
 eval $cmd				;# 6
```

### unset 删除变量

• unset这个命令从解释器中**删除变量**，它后面可以有任意多个参数，每个参数是一个变量名，可以是简单变量，也可以数组或数组元素。

```tcl
# 后面可以有任意多个参数，可以是简单变量，也可以数组或数组元素。
unset a b day(monday)
```

### appdend 加

• append命令**把文本加到一个变量的后面**

```tcl
set txt hello;    #hello
append txt"! How are you";   #hello! How are you
```

### incr 变量加整数

• incr命令把**一个变量值加上一个整数**。incr要求变量原来的值和新加的值都**必须是整数**。

```tcl
set b 2; 
incr b 3;   #结果为5
```

## 表达式

• TCL**支持常用的数学函数**，表达式中数学函数的写法类似于C\C++语言的写法，数学函数的参数可以是任意表达式，**多个参数之间用逗号隔开**。

```tcl
set x 2;    #变量x的值是2
expr 2* sin($x<3)； #表达式的值为1.68294196962

b = asin(1.68294196962/2);#matlab
b = 1
```

•其中expr是TCL的一个命令，语法为:expr arg ?arg ...?
­ 两个？之间的参数表示可省，后面介绍命令时对于可省参数都使用这种表示形式。

•需要注意的一点是，数学函数并不是命令，只在表达式中出现才有意义，即出现在expr之后才有意义。

##  array 数组 ()

**说是数组，其实也就比bat中的数组多了个索引可以被操作**

size

```tcl
#数组大小 
[array size varname]

set languages(0) Tcl
set languages(1) "C Language"
puts  [array size languages]
2
```

```tcl
#数组索引（Tcl的数组是通过字符串索引来访问的）
[array names variablename]

set personA(Name) "Dave"
set personA(Age) 14
set personA(Clase) 七
puts [array names personA]
puts $personA(1);	#这种写法是错误的
Age Name
```

for

```tcl
#数组迭代
set languages(0) Tcl
set languages(1) "C Language"
for { set index 0 }  { $index < [array size languages] }  { incr index } {
   puts "languages($index) : $languages($index)"
}
languages(0) : Tcl
languages(1) : C Language
```

在Tcl中，所有数组本质上都是关联的.无需任何特定顺序即可存储和检索数组.关联数组的索引不一定是数字，并且可以稀疏填充.

```tcl
#关联数组
set personA(Name) "Dave"
set personA(Age) 14
puts  $personA(Name)
puts  $personA(Age)
dave
14
```

foreach

通过数组的索引，遍历数组

> [array names personA]

```tcl
#关联数组的迭代
set personA(Name) "Dave"
set personA(Age) 14
foreach index [array names personA] {
   puts "personA($index): $personA($index)"
}
personA(Age): 14
personA(Name): Dave
```

##  string 字符串

### 字符串操作

| 命令                                   | 说明                                                         |
| -------------------------------------- | ------------------------------------------------------------ |
| **compare** string1 string2            | 以字面方式比较string1和string2.如果相等则返回0，<br />如果string1在string2之前返回，则返回-1，否则返回1. |
| **first** string1 string2              | 返回string2中第一次出现string1的索引.如果未找到，则返回-1.   |
| **index** string index                 | 返回索引处的字符                                             |
| **wordend** string index               |                                                              |
| **wordstart** string index             |                                                              |
| **last** string1 string2               | 返回string2中最后一次出现string1的索引.如果未找到，则返回-1. |
| **length** string                      | 返回字符串的长度.                                            |
| **match pattern** string               | 如果字符串与模式匹配，则返回1.                               |
| **range** string index1 index2         | 返回字符串中从index1到index2的字符范围.                      |
| **tolower** string                     | 返回小写字符串.(大写转小写)                                  |
| **toupper** string                     | 返回大写字符串.                                              |
| **trim** string？trimcharacters？      | 删除字符串两端的修剪字符.默认的修剪字符是空格.               |
| **trimleft** string？trimcharacters？  | 删除字符串左开头的修剪字符.默认的修剪字符是空格.             |
| **trimright** string？trimcharacters？ | 删除字符串左端的修剪字符.默认的修剪字符是空格.               |
| **wordend** findstring index           | 在包含索引处字符的单词后面的字符的findstring中返回索引.      |
| **wordstart** findstring index         | 返回包含索引处字符的单词中第一个字符的findstring中的索引.    |

```tcl
set s1 "Hello World"
set s2 "o"
puts [string first $s2 $s1]			;  #4
puts [string index $s1 0]			;  #H
puts [string last $s2 $s1]			;  #7
puts "Word end index in s1"			;  #Word end index in s1
puts [string wordend $s1 20]		;  #11
puts "Word start index in s1"		;  #Word start index in s1
puts [string wordstart $s1 20]		;  #6
puts [string length $s1]			; #11
puts [string toupper $s1]			; #HELLO WORLD
```

```tcl
#字符修剪
set s1 "Hello World"
set s2 "World"
puts "Trim right $s2 in $s1"
puts [string trimright $s1 $s2]

set s2 "Hello"
puts "Trim left $s2 in $s1"
puts [string trimleft $s1 $s2]

set s1 " Hello World "
set s2 " "
puts "Trim characters s1 on both sides of s2"
puts [string trim $s1 $s2]

Trim right World in Hello World
Hello 
Trim left Hello in Hello World
 World
Trim characters s1 on both sides of s2
Hello World
```

```tcl
#匹配字符串
set s1 "test@test.com" 
set s2 "*@*.com"
puts "Matching pattern s2 in s1"	;# Matchin
puts [string match "*@*.com" $s1 ]	;# 1
puts "Matching pattern tcl in s1"	;# Matchin
puts [string match {tcl} $s1]	    ;# 0
```

```tcl
#追加命令
set s1 "Hello" 
append s1 " World"
puts $s1
Hello World
```



```tcl
#字符串比较
string compare varname varname

set s1 "Hello"
set s2 "World"
set s3 "World"
puts [string compare s1 s2]
if {[string compare s2 s3] == 0} {
   puts "String \'s1\' and \'s2\' are same."; 
} 

if {[string compare s1 s2] == -1} {
   puts "String \'s1\' comes before \'s2\'.";
}

if {[string compare s2 s1] == 1} {
   puts "String \'s2\' comes after \'s1\'.";
}
-1
String 's1' comes before 's2'.
String 's2' comes after 's1'.
```

### 格式化命令 format

| Specifier |            说明            |
| :-------: | :------------------------: |
|    ％s    |         字符串表示         |
|    ％d    |          整数表示          |
|    ％f    |          浮点表示          |
|    ％e    | 带有尾数指数形式的浮点表示 |
|    ％x    |     十六进制十进制表示     |

```tcl
语法： format formatstring ?value devalue...?
#format命令类似于ANSIC中的sprintf函数，按formatstring提供的格式 ，把各个value的值组合到formatstring中形成一个新字符串返回。

puts [format "%f" 43.5]				;#	43.500000
puts [format "%e" 43.5]				;#	4.350000e+01
puts [format "%d %s" 4 tuts]		;#	4 tuts
puts [format "%s" "Tcl Language"]	;#	Tcl Language
puts [format "%x" 40]			    ;#	28
```

### 扫描命令 scan

```tcl
语法： scan string format varName ?varName...?
# scan命令可以认为是format命令的逆，其似于ANSIC中的scanf函数。它按format提供的格式分析string字符串，然后把结果存到变量varName中，注意除了空格和TAB键之外,string和format中的字符和'%'必须匹配。

puts [scan "90" {%[0-9]} m];	# 1
puts [scan "abc" {%[a-z]} m];	# 1
puts [scan "abc" {%[A-Z]} m];	# 0
puts [scan "ABC" {%[A-Z]} m];	# 1

scan "some 26 34" "some %d %d" a b         
set a 			;#26
set b    		;#34
```



## List 列表、集合{}

这些列表完全表示为字符串，并在需要时进行处理**以形成单个项目.**因此，在这种情况下避免使用大型列表;使用数组.

•list这个概念在TCL中是用来表示集合的。TCL中**list是由一堆元素组成的有序集合**，

**list可以嵌套定义，list每个元素可以是任意字符串，也可以是list**。

- 列表是一种有序的集合，其中的元素通过索引访问，**索引通常是整数**。
- 列表中的元素可以是任意类型的数据，包括字符串、整数、浮点数等。
- 列表的索引是**从0开始**的整数，通过索引可以获取、修改、删除列表中的元素。

| 关键词   | 说明                           | 举例                                                   |
| -------- | ------------------------------ | ------------------------------------------------------ |
| list     |                                |                                                        |
| concat   | 整合两个list                   | concat list list...                                    |
| lindex   | list的第lindex个元素           | lindex list index                                      |
| lassign  | 列表元素赋予  **独立索引变量** | lassign list variable1 variable2 ..                    |
| llength  | list的元素个数                 | llength list                                           |
| linsert  | 插入元素                       | linsert list index value value…                        |
| lset     | 插入元素                       | lset listname index value                              |
| lappend  |                                | lappend list value value...                            |
| lreplace | 替换指定索引位置元素           | lreplace listname firstindex lastindex value1 value2.. |
| lsort    | 排序                           | lsort listname                                         |

```tcl
#创建
set listName { item1 item2 item3 .. itemn }
set listName [list item1 item2 item3]
set listName [split "items separated by a character" split_character]

set colorList1 {red green blue}
set colorList2 [list red green blue]
set colorList3 [split "red_green_blue" _]
red green blue
```

```tcl
{}                                #空 list   

•语法：list  value value...
•这个命令生成list,就是所有的value。
 list 1 2 {3 4} ;   ;# list的元素是1 2 {3 4}
 
 #concat 整合两个list
•语法： concat list list...        
concat {1 2 3} {4 5 6}   ;#整合后的list为{1 2 3 4 5 6)

 #lindex 返回list的第lindex个元素
•语法： lindex list index         
 lindex {1 2 {3 4}} 2  ;#返回list的第2个元素3 4
 puts [lindex $var  1]
 
 #lassign 将列表转换为变量
 •语法： lassign list variable1 variable2 .. variablen
set var {orange blue red green}
lassign $var colour1 colour2
puts $colour1	;#orange
puts $colour2 	;#blue
 
 #llength 返回list的元素个数
•语法： llength list              
 llength {1 2 {3 4}} ;#3
 puts [llength $var]
 
 #linsert list插入元素
•语法： linsert list index value value…  
 linsert {1 2 5 6} 1 7 8  ;#1 7 8 2 5 6
 set var {orange blue red green}
 set var [linsert  $var 3 black white] ;#orange blue red black white green
 
 #lset 在索引处设置项目（注意这个）
 •语法： lset listname index value		
 set var {orange blue red green}
 lset var 0 black	;#black blue red green

 #把每个vaIue的值作为一个元素附加到变量vamame后面
• 语法： lappend list value value...
set var orange
append var " " "blue"
lappend var "red" 
lappend var "green"	;#orange blue red green

 #替换指定索引位置元素 at Indices
• 语法： lreplace listname firstindex lastindex value1 value2..valuen
set var {orange blue red green}
set var [lreplace $var 2 3 black white] ;#orange blue black white

#排序
• 语法： lsort listname
set var {orange blue red green}
set var [lsort $var] 	;#blue green orange red
```

## dict 字典

- 字典是一种**无序的键-值对集合**，其中的元素通过键来访问。
- 字典中的键和值可以是任意类型的数据。
- 字典提供了一种更灵活的方式来组织和检索数据，尤其适用于**需要根据特定键查找值**的情况。

字典是用于将值映射到键的布置.传统字典的语法如下所示 :

| 关键字       | 说明               | 举例                                              |
| ------------ | ------------------ | ------------------------------------------------- |
| dict set     |                    | dict set dictname key value                       |
| dict create  |                    | dict create dictname key1 value1 key2 value2 .... |
| dict size    | 长度               | dict size $colours                                |
| dict get     | 检索               |                                                   |
| dict values  | 字典中的**所有值** |                                                   |
| dict keys    | 字典中的**所有键** |                                                   |
| dict exists  | **检查键是否存在** |                                                   |
| foreach item | 字典迭代           |                                                   |



```tcl
#字典创建语法
dict set dictname key value
dict create dictname key1 value1 key2 value2 .. keyn valuen

#字典创建
dict set colours  colour1 red 
puts $colours	;# colour1 red
dict set colours  colour2 green
puts $colours	;# colour1 red colour2 green
set colours [dict create colour1 "black" colour2 "white"]
puts $colours	;# colour1 black colour2 white

#字典长度
puts [dict size $colours]	;# 2

#字典检索
语法： [dict get $dictname $keyname]
set value [dict get $colours colour1]	;# black	

#字典中的所有值
语法： [dict values $dictname]
set values [dict values $colours]	;# black white	

#字典中的所有键
语法： [dict keys $dictname]
set keys [dict keys $colours]	;# colour1 colour2

#检查键是否存在
语法： [dict exists $ dictname $ key]
set result [dict exists $colours colour1] 	；# 1

#字典迭代（打印键和字典值的简单字典迭代）
foreach item [dict keys $colours] {
   set value [dict get $colours $item]
   puts $value
}
 black 
 white
```



## 循环与判断

### if命令

TCL先把test1当作一个表达式求值，如果值非0。则把body1当作一个脚本执行并返回所得值，否则把test2当作一个表达式求值，如果值非0,则把body2当作一个脚本执行并返回所得值。

```tcl
语法： if test1 body1 else bodyn
if { $x>0 } {         #注意'{'一定要写在上一行,因为不这样，TCL解释器会认为if命令在换行符已经结束了；
···                #同时if和'{'之间应该有空格否则TCL解释器会把if'{'作为一个整体命令导致出错
					#（} {）俩个相背的花括号间也要有空格
} elseif {$x == 1} {
···} elseif {$x == 2} {  
···} else {
}

set a "10";
set b "10";
if {$a == $b} {
	puts [expr {$a==$b}]
} else {
	puts "aaa";
}
```

### while

**参数test是一个表达式，body是脚本**，如果表达式的值非0,就运行脚本，直到表达式为0才停止循环，此while命令中断并返回一个空字符串。此处是一个脚本：

```tcl
语法： while test body
set b " "	#空字符串，也就是没有任何字符的字符串。（在Tcl中，双引号用于表示字符串？）
set i [expr [llength $a] -1] #获取列表 a 的元素个数，并通过 expr 返回减一后的数据给 i
while {$i >= 0} {
	lappend b [lindex $a $i]	#返回列表a 中第i 个元素追加到 b的末尾
	incr i-1	#i-1 是一个字符串
	incr i -1 	#和下面一句话意思一样
	set i [expr {$i-1}] 	#这里的加减号俩边其实不需要空格（但可以有一种习惯）
}
〃变量a是一个链表，脚本把a的值复制到b
#按Ctrl&plus可以终止无限循环; C键
```

### for

- 参数init是一个初始化脚本，
- 第二个参数test是一个表达式 ，用来决定循环什么时候**中断**，
- 第三个参数reinit是重新初始化的脚本，
- 第四个参数body也是脚本，代表**循环体**；

假设变量a是一个链表，下面的脚本把a的值复制到b:

```tcl
语法： for init test reinit body
set b " "
for {set i [expr [llength $a] -1]} {$i>=0} {incr i -1} {
	lappend b [lindex $a $i] 
}
#作用和上面的例子是相同的。
 
#例如：
for {set i 0} {$i< 10} {incr i} {puts $i;}  #将打印出0到9
```

### foreach 迭代

- 第一个参数**varName是一个变量**，
- 第二个参数**list是一个表(有序集合)**，
- 第三个参数**body是循环体**。

每次取得链表的元素都会执行循环体一次。

```tcl
语法： foreach varName list body
set b " "
list a {a b c {a 1}}
foreach i a {
	set b [linsert $b 0 $i]	#从第 0个索引开始插入 $i
}					#变量a是一个链表，脚本把a的值复制到b。
```

### switch 命令

- 第一个是***\*可选\**参数options**,表示进行**匹配的方式**。TCL持三种匹配方式：**-exact方式，-glob方式，-regexp方式**,缺省情况表示-glob方式。
  - -exact方式表示的是精确匹配，
  - -glob方式的匹配方式和string match命令的匹配方式相同，
  - -regexp方式是正规表达式的匹配方式。
- **第二个参数string是要被用来作测试的值**，
- 第三个参数是括起来的**一个或多个元素对。**

```tcl
语法： switch options string ( pattern body pattern body ... }
switch $x {                   #一旦switch命令找到一个模式匹配
	b {incr t1}                   #就执行相应的脚本，并返回脚本的值，作为switch命令的返回值
	c {incr t2}                            
}  
switch $x {
	数值1 { 操作1 ;}
	数值2 { 操作2 ;}
}
```

•在循环体中，可以用**break**和**continue**命令中断循环。其中**break命令结束整个循环**过程并从循环中跳出**，continue只是结束本次循环**。

---



## proc 程序

程序只不过是具有一系列命令的代码块，这些命令提供了特定的可重用功能.它用于避免在多个位置重复相同的代码.程序等同于许多编程语言中使用的函数，并且在 **proc** 命令的帮助下在Tcl中可用.

```tcl
proc procedureName {arguments} {
   body
}

# 无参
proc helloWorld {} {
   puts "Hello, World!"	
}
helloWorld	;# Hello，World！

# 多参数
proc add {a b} {
   return [expr $a+$b]
}
puts [add 10 30]	;# 40
```

```tcl
# 带变量的程序参数
proc avg {numbers} {	;# numbers 是一个列表
   set sum 0
   foreach number $numbers {
      set sum  [expr $sum + $number]	;# 求和 
   }
   set average [expr $sum/[llength $numbers]] ;# 平均数
   return $average
}
puts [avg {70 80 50 60}]	;# 65 = (70 +80 +50 +60) /4 
puts [avg {70 80 50 }]		;# 66
```

```tcl
# 具有默认值的参数
proc add {a {b 100} } {	;# 这里的 {b 100} 并不是一个列表，而是列表中的一个 普通项，100是b的默认值
   return [expr $a+$b]
}
puts [add 10 30]	;# 40 = 10 + 30
puts [add 10]		;# 110 = 10 +100
```

```tcl
# 递归
proc factorial {number} {
   if {$number <= 1} {
      return 1
   } 
   return [expr $number * [factorial [expr $number - 1]]]
}

puts [factorial 3]	;# 6 = 3* (2* 1)
puts [factorial 5]	;# 120 = 5* (4* (3* (2* 1)))
```

## package 包

包用于创建可重用的代码单元. 包由一组提供特定功能的文件组成.此文件集合由包名称标识，
并且可以具有相同文件的多个版本.该包可以是Tcl脚本，二进制库或两者的组合的集合.

Package使用**命名空间**的概念来避免**变量名**和**过程名**的冲突. 在我们的下一个"名称空间"教程中查看更多内容.

### eval 创建包

可以在至少两个文件的帮助下创建包. 一个文件包含包代码. 其他文件包含用于声明包的索引包文件.

**步骤1:创建代码**

为文件夹内的包创建代码，说HelloWorld.让文件命名为HelloWorld.tcl，代码如下所示 :

```tcl
# /Users/rajkumar/Desktop/helloworld/HelloWorld.tcl 
# Create the namespace
namespace eval ::HelloWorld {	;# 为什么前面有冒号
 
  	# Export MyProcedure
  	namespace export MyProcedure
 
  	# My Variables
   	set version 1.0
   	set MyDescription "HelloWorld"
 
  	# Variable for the path of the script脚本路径的变量
   	variable home [file join [pwd] [file dirname [info script]]]
}
 
# Definition of the procedure MyProcedure
proc ::HelloWorld::MyProcedure {} {
	puts $HelloWorld::MyDescription		;# 为什么$ 和 hell 之间没有 ::
}

package provide HelloWorld $HelloWorld::version	;# 为什么$ 和 hell 之间没有 ::
package require Tcl 8.0
```

**第2步:创建包索引**

打开tclsh.切换到HelloWorld目录并使用pkg_mkIndex命令创建索引文件，如下所示 :

```tcl
% cd /Users/rajkumar/Desktop/helloworld 
% pkg_mkIndex . *.tcl
```

**第3步:向Autopath添加目录**

使用lappend命令将包添加到全局列表如下所示 :

```tcl
% lappend auto_path "/Users/rajkumar/Desktop/helloworld"
```

**第4步:添加包**

接下来使用package require语句将包添加到程序中，如下所示 :

```tcl
% package require HelloWorld 1.0
```

**第5步:调用过程**

现在，一切正在设置，我们可以调用我们的程序，如下所示 :

```tcl
% puts [HelloWorld::MyProcedure]	;# 输出：HelloWorld
```

前两步创建包.创建包后，您可以在任何Tcl文件中使用它，方法是添加最后三个语句，如下所示 :

```tcl
lappend auto_path "/Users/rajkumar/Desktop/helloworld"
package require HelloWorld 1.0
puts [HelloWorld::MyProcedure]		;# 输出：HelloWorld
```

### 命名空间

命名空间是一组标识符的容器，用于对变量和过程进行分组.
命名空间可从Tcl 8.0版获得.在引入名称空间**之前，存在单一的全局范围**.现在有了命名空间，我们**有了全局范围的附加分区**.

**创建命名空间**

```tcl
# 使用命名空间命令创建命名空间.
namespace eval MyMath {
  	# Create a variable inside the namespace
  	variable myResult
}

# Create procedures inside the namespace
proc MyMath::Add {a b } {  
  	set ::MyMath::myResult [expr $a + $b]
}
MyMath::Add 10 23	# 注意：直接调用时命名空间前面不需要加 '::'

puts $::MyMath::myResult	;# 输出：33
```

在上面的程序中，你可以看到有一个带变量的命名空间 **myResult** 和一个过程**添加.**  
这样就可以**在不同的命名空间下创建具有相同名称的变量和过程**.

**嵌套的Namesp aces**

Tcl允许嵌套命名空间.

```tcl
namespace eval MyMath {
   	# Create a variable inside the namespace
   	variable myResult
}

namespace eval extendedMath {
   	# Create a variable inside the namespace
   	namespace eval MyMath {
      	# Create a variable inside the namespace
      	variable myResult
   	}
}
set ::MyMath::myResult "test1"
puts $::MyMath::myResult					;# 输出：test1 
set ::extendedMath::MyMath::myResult "test2"
puts $::extendedMath::MyMath::myResult		;# 输出：test2
```

**导入和导出命名空间**

在之前的命名空间示例中，我们使用了**大量的范围解析运算符**，并且使用起来更复杂.我们可以通过**导入和导出名称空间来避免**。

```tcl
namespace eval MyMath {
   	# Create a variable inside the namespace
   	variable myResult
   	namespace export Add
}

# Create procedures inside the namespace
proc MyMath::Add {a b } {  
   	return [expr $a + $b]
}

namespace import MyMath::*
puts [Add 10 30]	;#输出：40
```

**忘记命名空间**

您可以使用删除导入的命名空间**忘记**子命令。

```tcl
namespace eval MyMath {
   	# Create a variable inside the namespace
   	variable myResult
   	namespace export Add
}

# Create procedures inside the namespace
proc MyMath::Add {a b } {  
   	return [expr $a + $b]
}
namespace import MyMath::*	;# 导入命名空间MyMath 中的啥了
puts [Add 10 30]		   ;# 输出：40
namespace forget MyMath::*	;# 删除
```

---



## 文件 I/O

Tcl在内置命令**open**，**read**，**puts**，**gets**、**close**的帮助下支持文件处理.

文件表示一个字节序列，如果它是无关紧要的是一个文本文件或二进制文件.

| 模式 | 说明                                                         |
| ---- | ------------------------------------------------------------ |
| r    | 打开现有文本文件以进行读取，**文件必须存在**.这是没有指定accessMode时使用的**默认模式**. |
| w    | 打开要写入的文本文件，**如果它不存在，则创建一个**新文件否则现有文件被截断. |
| a    | 打开文本文件以便以**附加模式写入**，文件必须存在.在这里，您的程序将开始在现有文件内容中附加内容 |
| r+   | 打开文本文件以进行**读写**.文件**必须已存在**.               |
| w+   | 打开文本文件以进行**读写**.如果它存在，它首先**将文件截断为零长度**，否则创建文件(如果它不存在). |
| a+   | 打开一个文本文件，用于读写.如果文件**不存在，将创建**该文件.**读数将从头开始**，但**只能附加写入**. |

**打开文件** open

**关闭文件** close

程序完成使用该文件后，必须关闭程序打开的任何文件.在大多数情况下，不需要明确关闭文件;
当File对象自动终止时，它们会自动关闭.

**编写文件** puts

Puts命令用于写入打开的文件. 编译并执行上述代码时，会创建在其下启动的目录中的新文件 **input.txt** (在程序的工作目录中).

**读取文件** set

```tcl
语法： open fileName accessMode
语法： close fileName
语法： puts $filename "text to write"
语法： set file_data [read $fp]
```

```tcl
set fp [open "input.txt" w+]
puts $fp "test"
close $fp

set fp [open "input.txt" r]
set file_data [read $fp]
puts $file_data		;# 结果：test
close $fp
```

```tcl
# 逐行读取文件直到文件结尾
set fp [open "input.txt" w+]
puts $fp "test\ntest"
close $fp

set fp [open "input.txt" r]
while { [gets $fp data] >= 0 } {
   puts $data
}
close $fp
```

```
test
test
```

### 2

• TCL提供了丰富的文件操作的命令。通过这些命令你可以对文件名进行操作（**查找匹配某一模式的文件）、以顺序或随机方式读写文件、检索系统保留的文件信息**（如最后访问时间）。

• TCL中文件名和我们熟悉的windows表示文件的方法有一些区别：在表示文件的目录结构时它使用'/'（linux终端文件目录也是用'/'）,而不是‘\’，

open name access
**open命令以\**access方式\**打开文件name。返回供其他命令（gets,close等）使用的文件标识。**

文件的打开方式和我们熟悉的c语言类似，有以下方式：

- r**只读**方式打开。文件**必须**已经**存在**。这是默认方式。
- r+**读写**方式打开，文件**必须**已经**存在**。
- w**只写**方式打开文件，如果文件存在则清空文件内容，**否则创建一个新的空文件**。
- w+**读写**方式打开文件，如**果文件存在则清空文件内容**，**否则创建新的空文件**。
- a只写方式打开文件，**文件必须存在**，并把指针指向文件尾。
- a+读写方式打开文件，**并把指针指向文件尾。如\**文件不存在，创建新的空文件\****

open命令返回一个字符串用于表识打开的文件

当调用别的命令（如：**gets,puts,close**〕对打开的文件进行操作时,就可以使用这个文件标识符。TCL有三个特定的文件标识：
**stdin**,**stdout**和**stderr**,分别对应**标准输入**、**标准输出**和**错误通道**，任何时候你都可以使用这三个文件标识。

**gets fileId varName**
读fileld标识的文件的下一行，忽略换行符。如果命令中**有varNam就把该行赋给它**，**并返回该行的字符数（文件尾返回-1）** ,如果**没有varName参数**，**返回文件的下一行作为命令结果**（如果到了文件尾，就返回空字符串）。

**puts -nonewline fileld string**
puts命令把string写到fileld中，如果没有nonewline开关的话，添加换行符。fileld默认是stdout。命令返回值为一空字符串。

**flush fileld **把缓冲区内容写到fileld标识的文件中，命令返回值为空字符串。
flush命令迫使缓冲区数据写到文件中，flush直到数据被写完才返回。当文件关闭时缓冲区数据会自动flush。

```tcl
proc tgrep { pattern filename} {
	set f [open $filename r]
	while { [gets $f line ] } {
		if {[regexp $ pattern $line]} {
			puts stdout $line
		}
	}
	close $f
}                              #TCL文件I/O的基本特点示例
```


• TCL提供两个命令来管理当前工作目录：pwd和cd。

pwd和UNIX下的pwd命令完全一样，没有参数，返回当前目录的完整路径。
cd 命令也和UNIX 命令也一样 ， 使用一个参数 ， 可以把工作目录改变为参数提供的目录 如果cd 没使用参数 ， UNIX下 ，会把工作目录变为启动TCL脚本的用户的工作目录。

• TCL提供了两个命令进行**文件名操作**：glob和file,**用来操作文件或获取文件信息**。

• [glob](https://so.csdn.net/so/search?q=glob&spm=1001.2101.3001.7020)命令采用一种或多种模式为参数，并返回匹配这个（些）模式的所有文件的列表


文件访问
**glob命令**的模式采用string match命令的匹配规则。例如：

```tcl
语法： glob switches pattern pattern ...

glob *.c *.h
main.c hash.c hash.h
```

• file delete *.tmp      #不生效   不执行通配符展开
先使用glob命令返回文件列表，在使用**参数展开语法{\*}**把列表元素作为独立参数提供给指令。

```tcl
file delete {*}[glob *.tmp]
```

也可以选择使用eval

```tcl
eval file delete [glob *.tmp]
```

file是有许多**选项的常用命令**，可以用来进行文件操作也可以检索文件信息。

```tcl
file atime name           #返回一个十进制的字符串，表示文件name最后被访问的时间。
```

时间是以秒为单位从1970年1月1日12:00AM开始计算。如果文件name不存在或查询不到访问时间就返回错误。例：

```tcl
file atime license.txt                        #975945600
file copy -force -- source target
#这个命令把source中指明的文件或目录递归的拷贝到目的地址
```

targetDir,只有当存在-force选项时，已经存在的文件才会被覆盖。试图覆盖一非空的目录或以文件覆盖一个目录或以一个目录覆盖一文件都会导致错误。

```tcl
file mkdir dir dir...           # 创建dir中指明的目录
file owned name             #如果name被当前用户拥有，返回1,否则返回0。
file executable name        #如果name对当前用户是可以执行的，就返回1,否则返回0。
```

### 相关命令

![image-20230801173708664](https://gitee.com/jiagnkun/procotol_device/raw/master/Typora/DaLei/assic.picture/202308011737917.png)

![image-20230801173530819](https://gitee.com/jiagnkun/procotol_device/raw/master/Typora/DaLei/assic.picture/202308011735138.png)

---



## 错误处理

在**错误**和 **catch** 命令的帮助下提供了Tcl中的错误处理.每个命令的语法如下所示.

**错误语法**

```tcl
error message info code
# message 是错误消息，
# info在全局变量 errorInfo 中设置，
# 代码在全局变量 errorCode 中设置.
```

在上面的错误命令语法中，message是错误消息，info在全局变量errorInfo中设置，代码在全局变量errorCode中设置.

**Catch语法**

```tcl
catch script resultVarName
# script是要执行的代码，
# resultVarName是保存错误或结果的变量.
# 如果没有错误，catch命令返回0，如果有错误，则返回1.
```

在上面的catch命令语法中，script是要执行的代码，resultVarName是保存错误或结果的变量.如果没有错误，catch命令返回0，如果有错误，则返回1.

```tcl
# 错误处理的示例
proc Div {a b} {
   	if {$b == 0} {
   		# error message 				info 				  code
      	error "Error generated by error" "Info String for error" 401
   	} else {
      	return [expr $a/$b]
   	}
}

# 	catch  script 					  resultVarName
if {[catch {puts "Result = [Div 10 0]"} errmsg]} { 	;# 将 script 执行后的结果，error语法 中的 message，返回给 errmsg
   	puts "ErrorMsg: $errmsg"
   	puts "ErrorCode: $errorCode"	;# 将 script 执行后的结果，error语法 中的 code，返回给 errorCode
   	puts "ErrorInfo:\n$errorInfo\n"
}

if {[catch {puts "Result = [Div 10 2]"} errmsg]} {	;# 没有错误 catch 返回0，所以不执行此语句
   	puts "ErrorMsg: $errmsg"
   	puts "ErrorCode: $errorCode"
   	puts "ErrorInfo: $errorInfo\n"
}
```

```tcl
ErrorMsg: Error generated by error
ErrorCode: 401
ErrorInfo: Info String for error
   (procedure "Div" line 1)
   invoked from within
"Div 10 0"

Result = 5
```

在上面的示例中，我们可以创建自己的自定义错误消息. 

类似地，也可以捕获由Tcl生成的错误.示例如下所示 :

```tcl
catch {set file [open myNonexistingfile.txt]} result ;# 不加上 result 就无法输出错误信息，为什么呢？
puts "ErrorMsg: $result"
puts "ErrorCode: $errorCode"
puts "ErrorInfo:\n$errorInfo\n"
```

```tcl
ErrorMsg: couldn't open "myNonexistingfile.txt": no such file or directory
ErrorCode: POSIX ENOENT {no such file or directory}
ErrorInfo:
couldn't open "myNonexistingfile.txt": no such file or directory
   while executing
"open myNonexistingfile.txt"
```

## 内置函数

Tcl为各种操作提供了许多内置函数(过程).这包括 :

- list 处理.
- string的功能处理.
- 数组处理.
- 词典处理的功能.
- 文件I/O 处理的功能.
- 用于创建名称空间和包.
- 数学运算的函数.
- 系统操作的功能.

### 数字运算函数

| 函数             | 说明                                                         |
| ---------------- | ------------------------------------------------------------ |
| abs arg          | 绝对值                                                       |
| sqrt arg         | 计算平方根arg. arg必须是正面的.                              |
| asin、acos、atan | 反正余弦、计算反义词 arg                                     |
| atan2 yx         | 计算其参数(y/x)的商的反正切值.                               |
| cosh arg         | arg 的双曲余弦值                                             |
| double arg       | arg是否为浮点值，返回arg，否则将arg转换为浮点并返回转换后的值. |
| exp arg          | 一个指数函数(e提高到arg的幂).                                |
| pow xy           | 计算x增加到幂y的值.如果x为负数，则y必须为整数值.             |
| ceil arg         | 大于或等于数字的最小整数                                     |
| floor arg        | 小于或等于arg的最大整数.                                     |
| fmod xy          | 浮点余数x的除法.如果y为0，则返回错误.                        |
| hypoy xy         | 直角三角形sqrt的斜边长度(x * x + y * y).                     |
| log arg          | arg的自然对数.                                               |
| log10 arg        | 基数10 arg的对数.                                            |
| rand             | 计算0到1之间的伪随机数                                       |
| srand arg        | 计算0到1之间的伪随机数.arg必须是整数，用于重置rand随机数生成器的种子. |
| round arg        | 计算0到1之间的伪随机数                                       |
| 宽 arg           | 计算至少64位宽的整数值(如果arg是a，则通过符号扩展计算如果arg已经不是一个，则为32位数字. |

```tcl
namespace import ::tcl::mathfunc::*	
puts [tan 10]	                   	;# 0.6483608274590866
puts [pow 10 2]	                   	;# 100.0
puts [ceil 10.34]	               	;# 11.0
puts [hypot 10 20]	               	;# 22.360679774997898
puts [log 10]	                   	;# 2.302585092994046
puts [srand 45]	                   	;# 0.0003521866166741525
```

- `double()`将数字转换为浮点数。
- `int()`将数字转换为普通整数（通过*截断*小数部分）。
- `wide()`将数字转换为所谓的宽整数（这些数字具有更大的范围）。





### 系统函数 exec

`exec` 是一个用于在操作系统上执行外部命令的命令。它允许你在Tcl脚本中调用操作系统的命令行程序，并从Tcl脚本中获取命令的输出或向命令传递输入。

```tcl
exec ?switches? program ?arg ...?
```

- `switches`: 可选参数，用于指定一些选项。常用的选项有：
  - `-ignorestderr`: 忽略来自程序的标准错误输出。
  
  - `-ignorestatus`: 忽略程序的退出状态，即使命令执行失败也不会产生错误。
  
- `program`: 要执行的外部命令或程序。
- `arg ...`: 可选参数，用于传递给外部命令的参数。

演示如何使用 `exec` 命令调用操作系统的命令 `ls` 来列出当前目录的文件和子目录：

```tcl
set result [exec ls]	;#exec ls 将执行操作系统的 ls 命令
puts $result
```

Tcl中的重要系统函数包括，

- **时钟** : 秒函数，以秒为单位返回当前时间.
- **时钟** : 格式函数，将秒格式化为日期和时间.
- **时钟** : 扫描功能，扫描输入字符串并将其转换为秒.
- **打开** : 函数，用于打开文件.
- **exec** :  function，用于执行系统命令.
- **关闭** : 函数，用于关闭文件.

```tcl
#get seconds
set currentTime [clock seconds]
puts $currentTime
#get format 
puts "The time is: [clock format $currentTime -format %H:%M:%S]"	;# The time is: 03:09:16
puts "The date is: [clock format $currentTime -format %D]"			;# The date is: 07/31/2023

set date "Jun 15, 2014"
puts [clock scan $date -format {%b %d, %Y}]		;# Jun 15, 2014

puts [exec ls]
puts [exec dir]

set a  [open input.txt]
puts [read $a];			
puts $a			;#file3
close $a
```

```tcl
1402819756
The time is: 03:09:16
The date is: 06/15/2014
1402808400
input.txt
main.tcl
input.txt  main.tcl
This is the file you can use to provide input to your program and later on open
   it inside your program to process the input.

file3
```

### 格式化时间和日期

| Sr.No. |      |              格式&说明              |
| :----- | ---- | ---- |
| 1      |      |   **％a**日期缩短形式，例如:Sun.    |
| 2      |      |      **％A**完整日例如:星期天.      |
| 3      |      |          **％b**缩短月份.           |
| 4      |      |         **％B**月完整形式.          |
| 5      |      |            **％d**日期.             |
| 6      |      |        **％j**朱利安日一年.         |
| 7      |      |           **％m**月份数.            |
| 8      |      |         **％y**两年级数字.          |
| 9      |      |        **％Y**第一年n四位数.        |
| 10     |      |        **％H**24小时制小时.         |
| 11     |      |       **％I**12小时制的小时.        |
| 12     |      |            **％M**分钟.             |
| 13     |      |             **％S**秒.              |
| 14     |      |           **％p**AM或PM.            |
| 15     |      |     **％D**日期数量，mm/dd/yy.      |
| 16     |      |       **％r**12小时制的时间.        |
| 17     |      |   **％R**没有秒的24小时制的时间.    |
| 18     |      |     **％T**24小时制时间，秒数.      |
| 19     |      | **％Z**时区名称，如GMT，IST，EST等. |

## 正则表达式 regexp

"**regexp**" 命令用于匹配Tcl中的正则表达式. 
正则表达式是包含搜索模式的字符序列.它由多个规则组成。

| Sr .No. |                          规则&说明                           |
| :------ | ---- |
| 1       |                        **x**完全匹配.                        |
| 2       |                **[az]**来自az的任何小写字母.                 |
| 3       |                        **.**任何角色.                        |
| 4       |                    **^**起始字符串应匹配.                    |
| 5       |                    **$**结束字符串应匹配.                    |
| 6       |     **\ ^**支持特殊字符的间隙序列^.同样可以用于其他字符.     |
| 7       |         **()**在括号内添加上述序列以制作正则表达式.          |
| 8       |               **x \***应该匹配0或更多前面的x.                |
| 9       |             **x+**应匹配前一个x的一次或多次出现.             |
| 10      |             **[az]？**应匹配前一个x的0或1次出现.             |
| 11      | **{digit }**匹配前一个正则表达式的完全数字出现次数.包含0-9的数字. |
| 12      | **{digit，}**匹配前一个正则表达式的3位或更多位数.包含0-9的数字. |
| 13      | **{digit1，digit2}**出现次数匹配前一个正则表达式的digit1和digit2次出现之间的范围. |

这里，正则表达式是命令. 我们稍后会看到可选开关. 模式是前面提到的规则. 搜索字符串是执行正则表达式的实际字符串. 完全匹配是保存匹配的正则表达式结果的任何变量. Submatch1到SubMatchn是可选的subMatch变量，它保存子匹配模式的结果.

包含任何字母的字符串的简单示例. 当遇到任何其他字符的正则表达式时，搜索将被停止并返回.

```tcl
语法： regexp optionalSwitches patterns searchString fullMatch subMatch1 ... subMatchn

regexp {([A-Z,a-z]*)} "Tcl Tutorial" a b 
puts "Full Match: $a"	;# Full Match: Tcl
puts "Sub Match1: $b"	;# Sub Match1: Tcl
```

### 多种模式

以下示例显示如何搜索多个模式. 这是任何字母 后跟任何字符 后跟任何字母的示例模式.

```tcl
regexp {([A-Z,a-z]*).([A-Z,a-z]*)} "Tcl Tutorial" a b c  
puts "Full Match: $a"	;# Full Match: Tcl Tutorial
puts "Sub Match1: $b"	;# Sub Match1: Tcl
puts "Sub Match2: $c"	;# Sub Match2: Tutorial
```

上面代码的修改版本显示子模式可以包含多个模式，如下所示 :

```tcl
regexp {([A-Z,a-z]*.([A-Z,a-z]*))} "Tcl Tutorial" a b c  
puts "Full Match: $a"	;# Full Match: Tcl Tutorial
puts "Sub Match1: $b"	;# Sub Match1: Tcl Tutorial
puts "Sub Match2: $c"	;# Sub Match2: Tutorial
```

### 正则表达式命令的开关

Tcl中可用的开关列表是，

- **nocase** : 用于忽略大小写.
- **indices** : 存储匹配的子模式的位置而不是匹配的字符.
- **行** : 新的线敏感匹配.在换行后忽略字符.
- **开始索引** : 设置搜索模式开始的偏移量.
- 标记开关的结尾

在上面的例子中，我故意在所有字母表中使用[AZ，az]，你可以很容易地使用 -nocase 而不是如下所示 :

```tcl
regexp -nocase {([A-Z]*.([A-Z]*))} "Tcl Tutorial" a b c  
puts "Full Match: $a"	;# Full Match: Tcl Tutorial
puts "Sub Match1: $b"	;# Sub Match1: Tcl Tutorial
puts "Sub Match2: $c"	;# Sub Match2: Tutorial
```

使用开关的另一个例子如下所示 :

```tcl
regexp -nocase -line -- {([A-Z]*.([A-Z]*))} "Tcl \nTutorial" a b 
puts "Full Match: $a"	;# Full Match: Tcl
puts "Sub Match1: $b"	;# Sub Match1: Tcl
regexp -nocase -start 4 -line -- {([A-Z]*.([A-Z]*))} "Tcl \nTutorial" a b  
puts "Full Match: $a"	;# Full Match: Tutorial
puts "Sub Match1: $b"	;# Sub Match1: Tutorial
```



[Tcl脚本入门笔记详解（一）_tcl脚本语言_一点一点的进步的博客-CSDN博客](https://blog.csdn.net/yh13572438258/article/details/123353265?ops_request_misc=%7B%22request%5Fid%22%3A%22168636216916800197058147%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=168636216916800197058147&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123353265-null-null.142^v88^control_2,239^v2^insert_chatgpt&utm_term=TCL脚本&spm=1018.2226.3001.4187)

[Tcl脚本入门笔记详解（二）_tcl global变量_一点一点的进步的博客-CSDN博客](https://blog.csdn.net/yh13572438258/article/details/123373034?ops_request_misc=&request_id=203bd15c819d46d3b7dca17c430d1c33&biz_id=&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~koosearch~default-2-123373034-null-null.268^v1^control&utm_term=Tcl脚本&spm=1018.2226.3001.4450)

[Tcl - 内置函数 - IT宝库 (itbaoku.cn)](https://www.itbaoku.cn/tutorial/tcl_tk-tcl_builtin_functions.html)



# 工程实例

## 图像预处理与仿真

```tcl
# 调用Matlab的gray_pretreatment.m进行图片预处理
proc matlab_gray_pretreatment {} {
	set cmd "m:/mat/matlab.exe -nodisplay -nosplash -nodesktop -r \"run('c:/a/gray_pretreatment.m')\""
    # set cmd "matlab -nodisplay -nosplash -nodesktop -r gray_pretreatment"
    exec $cmd
    exit		;# 确保执行完 .m脚本中的命令后，会终止MATLAB会话并返回到Tcl脚本中继续执行后续的命令
}

# 调用Vivado的tb_gray.v进行仿真
proc vivado_tb_gray_simulation {}
	set cmd "v:/viv/vivado.exe -mode batch -source c:/v/tb_gray.tcl"/
    # set cmd "vivado -mode batch -source tb_gray.tcl"
    exec $cmd
}

# 调用Matlab的sim_gray.m进行后仿真处理
proc matlab_sim_gray_processing {} {
    set cmd "matlab -nodisplay -nosplash -nodesktop -r sim_gray"
    exec $cmd
}

# 主程序，执行整个自动仿真过程
proc main {} {
    matlab_gray_pretreatment	;# 调用Matlab进行图片预处理，生成gray.txt
    vivado_tb_gray_simulation	;# 调用Vivado进行仿真，生成sim_gray.txt
    matlab_sim_gray_processing	;# 调用Matlab进行后仿真处理，生成sim_gray.png
    puts "FPGA自动仿真完成！"
}

main	;# 运行主程序
# --------------------------------------------------------
    # 将仿真后的图片从c:/v/sim_gray.png复制到c:/b/sim_gray.png
    # file copy -force c:/v/sim_gray.png c:/b/sim_gray.png
```

**解释**

```tcl
set cmd "m:/mat/matlab.exe -nodisplay -nosplash -nodesktop -r \"run('c:/a/gray_pretreatment.m')\""
```

ChatGPT

这段代码是一个Tcl命令，用于调用Matlab可执行文件执行脚本`gray_pretreatment.m`。

1. `set cmd "m:/mat/matlab.exe ..."`: 这是一个Tcl命令，使用`set`命令将一个字符串赋值给变量`cmd`。这个字符串是要执行的Matlab命令行的完整命令，其中`m:/mat/matlab.exe`是Matlab可执行文件的路径。
2. `-nodisplay -nosplash -nodesktop`: 这些是Matlab的命令行选项。它们用于在Matlab的命令行模式下运行，而不显示任何图形用户界面。具体含义如下：
   - `-nodisplay`: 禁用Matlab的显示功能，这样在命令行中运行时不会显示图形窗口。
   - `-nosplash`: 禁用Matlab的启动画面，这样在命令行中运行时不会显示欢迎界面。
   - `-nodesktop`: 禁用Matlab的桌面模式，这样在命令行中运行时不会启动Matlab的桌面环境。
3. `-r \"run('c:/a/gray_pretreatment.m')\"`: 这是Matlab的命令行选项，用于在Matlab中运行指定的脚本文件`gray_pretreatment.m`。具体含义如下：
   - `-r`: 后面跟着要执行的Matlab命令。
   - `run('c:/a/gray_pretreatment.m')`: 这是要在Matlab中执行的命令。`run`是Matlab的内置函数，用于运行指定的脚本文件。

综合起来，这段Tcl命令将调用Matlab的可执行文件`m:/mat/matlab.exe`，在Matlab命令行中执行`gray_pretreatment.m`脚本文件，并且在执行过程中禁用了Matlab的图形显示功能和桌面环境，以实现在命令行模式下自动化运行Matlab脚本。

```tcl
set cmd "v:/viv/vivado.exe -mode batch -source c:/v/tb_gray.tcl"
```

ChatGPT

 这段代码是一个Tcl命令，用于调用Vivado可执行文件执行`tcl`脚本`tb_gray.tcl`。

1. `set cmd "v:/viv/vivado.exe ..."`: 这是一个**Tcl命令**，使用`set`命令将一个字符串赋值给变量`cmd`。这个字符串是要执行的Vivado可执行文件的完整命令，其中`v:/viv/vivado.exe`是Vivado可执行文件的路径。
2. `-mode batch`: 这是Vivado的**命令行选项**。它用于指定Vivado在批处理模式下运行，而不会启动图形用户界面。
3. `-source c:/v/tb_gray.tcl`: 这是Vivado的**命令行选项**，用于指定要执行的`tcl`脚本文件`tb_gray.tcl`。Vivado会按照脚本中的指令自动进行仿真等操作。

综合起来，这段Tcl命令将调用Vivado的可执行文件`v:/viv/vivado.exe`，在批处理模式下运行Vivado，并执行`tcl`脚本`tb_gray.tcl`。通过执行这个脚本，Vivado会自动进行仿真等操作，根据脚本中的指令进行设计工程的模拟和验证。这样可以实现自动化运行Vivado工程，而无需手动打开Vivado图形界面进行操作。

































```tcl
# Name: John, Age: 30, Occupation: Engineer
# 打开文件并读取一行数据
set fileId [open "data.txt" r]
gets $fileId line
close $fileId

# 在该行数据中查找"Name"字段对应的值
set nameValue [string match *Name:* $line]
if {$nameValue ne ""} {
    # 提取"Name"字段对应的值
    set name [string trimleft $nameValue "Name: "]
    puts "Name: $name"
} else {
    puts "Name not found in the line."
}

```

