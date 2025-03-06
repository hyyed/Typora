# 批处理文件

https://www.cnblogs.com/klchang/p/4771101.html



## 常见命令

| windows命令行                      | 功能描述                 | linux终端 |
| ---------------------------------- | ------------------------ | --------- |
| cd                                 | 切换工作目录             | cd        |
| dir/s                              | 列出当前文件夹下所有文件 | ls [-lh]  |
| type                               | 查看文件内容             | cat       |
| md/mkdir                           | 创建目录                 | mkdir     |
| .>file.txt                         | 创建文件                 |           |
| del                                | 删除文件而不删除目录.    | rm        |
| rd                                 | 删除目录                 | rm -r     |
| copy/xcopy                         | 拷贝                     | cp [-r]   |
| cls                                | 清屏                     | clear     |
| findstr                            | 根据关键字查找           | grep      |
| move/rename                        | 移动/重命名              | mv/rename |
| tasklist                           | 查找进程                 | ps [-ef]  |
| taskkill                           | 杀死进程                 | kill [-9] |
| D:                                 | 进入D盘                  |           |
| ipconfig                           |                          |           |
| netstat /an                        | 输出所有网络连接         |           |
| netstat /an \| find  “ESTABLISHED” | 筛选出所有建立连接的网络 |           |

文件操作

| win命令                 | 作用         | 扩展                                             | linux |
| ----------------------- | ------------ | ------------------------------------------------ | ----- |
| start                   | 打开新的CMD  | start.：打开所在文件夹                           |       |
| echo 文本内容 > 文件名  | 写内容       | “文件名”：包含特殊字符或空格<br />echo.   ：空行 |       |
| echo 文本内容 >> 文件名 | 追加内容     |                                                  |       |
| pause                   | 按任意键继续 |                                                  |       |
| exit                    | 退出CMD      | exit /B 1 返回错误级别                           |       |



| S.No | 命令           | 说明                                                         |
| :--- | -------------- | ------------------------------------------------------------ |
| 1    | VER            | 显示您正在使用的MS-DOS版本.                                  |
| 2    | ASSOC          | 它将扩展名与文件类型(FTYPE)相关联，显示现有关联或删除关联.   |
|      |                |                                                              |
|      |                |                                                              |
|      |                |                                                              |
| 6    |                |                                                              |
| 7    | time           | 修改系统时间                                                 |
| 8    | DATE           | 有助于查找系统日期.                                          |
| 9    | ECHO           | 显示消息，或转动命令回显或者关闭.                            |
| 10   | EXIT           | 退出DOS控制台.                                               |
| 11   |                |                                                              |
| 12   |                |                                                              |
| 13   | PATH           | 显示或设置路径变量.                                          |
| 14   | PAUSE          | 此批次comman d提示用户并等待输入一行输入.                    |
| 15   | PROMPT         | 可用于更改或重置cmd.exe提示.                                 |
| 1    |                |                                                              |
| 17   | REN            | 重命名文件和目录                                             |
| 18   | REM            | 用于批处理文件中的备注，防止备注内容被执行.？                |
|      |                |                                                              |
| 20   | TIME           | 设置或显示时间.                                              |
| 21   |                |                                                              |
| 22   | VOL            | 显示卷标.                                                    |
| 23   | ATTRIB         | 显示或设置a curret目录中文件的属性                           |
| 24   | CHKDSK？       | 检查磁盘是否存在问题.                                        |
| 25   | CHOICE         | 为用户提供选项列表.                                          |
| 26   | CMD此          | 用另一个命令提示符实例.                                      |
| 27   | COMP           | 根据文件大小比较2个文件.                                     |
| 28   | CONVERT        | 将卷从FAT16或FAT32文件系统转换为NTFS文件系统.                |
| 29   | DRIVERQUERY    | 显示所有已安装的设备驱动程序及其属性.                        |
| 30   | EXPAND         | 从压缩的.cab cabinet文件中提取文件.                          |
| 31   | FIND           | 在文件中搜索字符串或输入，输出匹配的行.                      |
| 32   |                | 格式此批处理命令将磁盘格式化为使用Windows支持的文件系统，如FAT，FAT32或NTFS，从而覆盖以前的磁盘内容. |
| 33   |                | 帮助此批处理命令显示Windows提供的命令列表.                   |
| 34   | IPCONFIG       | 显示Windows IP配置.按连接显示配置和该连接的名称.             |
| 35   | LABEL          | 可添加，设置或删除磁盘标签.                                  |
| 36   | MORE           | 一次显示一个或多个文件的内容.                                |
| 37   | NET            | 服务，具体取决于所使用的命令.                                |
| 38   | PING           | 通过网络将ICMP/IP"echo"数据包发送到指定地址.                 |
| 39   | SHUTDOWN       | 关闭计算机，或注销当前用户.                                  |
| 40   | SORT           | 接受来自的输入一个源文件，按字母顺序对其内容进行排序，从A到Z或Z到A.它在控制台上打印输出. |
| 41   | SUBST          | 将驱动器号分配给本地文件夹，显示当前分配或删除分配.          |
| 42   | SYSTEMINFO     | 显示计算机及其操作的配置ating system.                        |
| 43   | TASKKILL       | 结束一项或多项任务.                                          |
| 44   | TASKLIST       | 列出任务，包括任务名称和进程ID(PID).                         |
| 45   | XCOPY          | 以更高级的方式复制文件和目录.                                |
| 46   | TREEthis batch | 命令将当前目录的所有子目录的树显示为任何级别的递归或深度.    |
| 47   | FC             | 列出了两个文件之间的实际差异.                                |
| 48   | DISKPART       | 显示和配置磁盘分区的属性.                                    |
| 49   | TITLE          | 设置控制台窗口中显示的标题.                                  |
| 50   | SET            | 显示当前系统上的环境变量列表.                                |

**dir扩展**

- `/B`：以简洁格式显示文件名，只列出文件名而不显示其他信息。
- `/S`：在子文件夹中递归显示文件。
- `/A`：指定要显示的文件的属性，例如 `/A:D` 显示只显示文件夹，`/A:-D` 显示除文件夹外的其他文件。
- `/O`：指定按照哪种方式排序，例如 `/O:N` 按名称排序，`/O:D` 按日期排序。

你可以通过在命令提示符中输入 `dir /?` 来查看更多 `dir` 命令的选项和用法。

## 第一批脚本程序

让我们先构建我们的简单批处理脚本程序.打开记事本并输入以下代码行.将文件另存为"List.cmd".

代码执行以下操作 :

- 使用echo off命令确保在执行代码时不显示命令.
- Rem命令用于添加注释说明这个批处理文件究竟是做什么的.
- dir 命令用于获取位置C:\Program Files的内容.
- '>' 命令用于将输出重定向到文件C:\ lists.txt.
- 最后，echo命令用于告诉用户操作已完成.

```cmd
@echo off 
:: This is for listing down all the files in the directory Program files 
dir "D:\Program Files" > D:\file.txt 
echo "The program has completed"
@echo on

:: 执行上述命令时，C中的文件名称:\程序文件将被发送到文件D:\ Lists.txt，并在命令提示符中显示消息"程序已完成".
```



---

## 概述

批处理脚本用于自动化命令序列，这些命令序列本质上是重复的.脚本是一种可以通过自动化这些命令序列来减轻这种必要性的方式，以便使shell的生命更容易，更高效.在大多数组织中，批处理脚本以某种方式被合并以自动化东西.

批处理脚本的一些功能是 :

- 可以读取用户的输入，以便进一步处理.
- 具有控制结构等至于，if，while，切换以获得更好的自动化和脚本编写.
- 支持函数和数组等高级功能.
- 支持正则表达式.
- 可以包含其他编程代码，例如Perl.

批处理脚本的一些常见用法是 :

- 为不同目的设置服务器.
- 自动执行内务活动，例如删除不需要的文件或日志文件.
- 自动将应用程序从一个环境部署到另一个环境.
- 一次在各种机器上安装程序.

批处理脚本存储在简单的文本文件中，其中包含的命令行依次按顺序执行.这些文件具有特殊扩展名BAT或CMD.通过称为**命令解释器的系统文件提供的接口(有时称为shell)来识别和执行此类型的文件.**在Windows系统上，此解释器称为cmd.exe.

运行批处理文件只需单击即可. 批处理文件也可以在**命令提示符**或**Start-Run行中**运行. 在这种情况下，**必须使用完整路径名**，**除非文件的路径在路径环境中**.

```cmd
:: 运行时此批处理脚本将删除当前目录中的所有文件.
:: Deletes All files in the Current Directory With Prompts and Warnings
::(Hidden, System, and Read-Only Files are Not Affected)
:: @ECHO OFF
DEL . DR
```



---

## 变量

批处理文件中有两种类型的变量。 其中一个参数是在调用批处理文件时可以传递的参数，另一个是通过`set`命令完成的。

### 命令行参数

批处理脚本支持**命令行参数的概念**，其中参数可以在被调用时传递给批处理文件。参数可以通过变量`％1`，`％2`，`％3`等从批处理文件中调用。

以下示例显示了一个批处理文件，它接受3个命令行参数，并将它们回显到命令行屏幕。

```bat
:: bat
@echo off 
:: 命令行参数的概念
echo %1 
echo %2 
echo %3
Bat
```

如果上面的批处理脚本存储在一个名为`test.bat`的文件中，我们将运行该批处理 - 

```cmd
:: cmd
Test.bat a 5 6
a
5
6
```

### set

```cmd
语法： set /A variable-name=value
```

- *variable-name* - 是想要设置的变量的名称。
- *value* - 是需要根据变量设置的值。
- */A* - (可选)如果该值本质上是数值，则使用此开关。

```cmd
set a=5
set b=10
set c= %a% - %b%	:: %n%,类似TCL的变量置换$
set /a d= %a% - %b%	:: /A,类似TCL的命令置换 expr
set /p d= 等待用户输入（默认值为上）
echo c		:: c
echo %c%	:: 5-10	::类似TCl的输出puts
echo d		:: d
echo %d%	:: -5
```

### 全局与局部变量

DOS脚本还定义了局部和全局范围的变量。 **默认**情况下，变量是整个命令提示符会话的**全局变量**。 调用`**SETLOCAL**`命令，使变量**局部**在脚本的范围内。 在调用`SETLOCAL`之后，任何变量赋值在调用`ENDLOCAL`，调用`EXIT`，或者当执行到达脚本中的文件结尾(EOF)时都会返回。 

```cmd
@echo off 
set globalvar=5
SETLOCAL
	set var=45
	set /A var=%var% + 5
	echo %var%			:: 50
	echo %globalvar%	:: 5
ENDLOCAL
echo %var%			::echo处于关闭状态
```

- `'globalvar'`是用全局范围定义的，在整个脚本中都是可用的。
- `var`变量是在局部范围内定义的，因为它被包含在`SETLOCAL`和`ENDLOCAL`块之间。 因此，这个变量在执行`'ENDLOCAL'`语句后就会被销毁。

### 系统环境变量

```
echo %系统环境变量名称%
打印：系统环境变量值
```



---

## 字符串

### 基本操作

```bat
:: 空字符串
set a=Hello World	::与TCL不同，CMD能识别 等于号 和空格
if [%a%]==[] echo "String A is empty"

:: 插入字符
SET /a d=50 
SET c=%a% and %d%
echo %c%	:: Hello World and 
```

### 字符长度 ？

在DOS脚本中，没有定义用于查找字符串长度的长度函数。 可以使用**自定义的函数**实现这个目的。 以下是用于查看字符串长度的自定义函数 

```bat
@echo off
set str=Hello World
call :strLen str strlen
echo String is %strlen% characters long
exit /b

:strLen
setlocal enabledelayedexpansion

:strLen_Loop
   if not "!%1:~%len%!"=="" set /A len+=1 & goto :strLen_Loop
(endlocal & set %2=%len%)
goto :eof
```

- 计算字符串长度的代码在`strLen`块中定义。
- 字符串的长度保存在变量`len`中。

### 字符检索

```bat
@echo off 
:: 检索
set x=1000 
set y=123456
set y1=%y1:~-4% 	:: 从右往左检索
set	y2=%y:~1,4%		:: 从左边第二个往右检索4个
echo %x% 	:: 1000
echo %y%	:: 123456
echo %y1%	:: 3456
echo %y2%	:: 2345
::将空格添加到`y`的变量中，在这示例中是将`9`个空格添加到`y`的变量中。

:: 删除
set del1=%y:123=%	:: 删除指定字符（即替换为空字符）
set del2=%y:~1,-2%	:: 删除左边一个，右边俩个字符
set del3=%str: =%	:: 删除所有空格（:与=之间有一个空格）
echo %del1%		:: 456
echo %del2%		:: 234

:: 替换
set del4=%y:123=456%
echo %del4%
```



---

## 数组

### 数组遍历 for

```bat
@echo off 
REM 在启用了延迟扩展的环境中，你可以使用 ! 符号来扩展变量的值，而不是传统的 % 符号。
setlocal enabledelayedexpansion
set "list=11 22 33 44"
REM 语法：for %%variable in (set) do command
REM set 是要循环遍历的元素集合，可以是文件列表（使用通配符）、目录列表、命令输出（使用反引号）或是手动指定的一组字符串。
for %%a in (%list%) do (
	echo 数组list[%%a]=!list!
)
endlocal
::"数组list[11]=11 22 33 44"
::"数组list[22]=11 22 33 44"
::"数组list[33]=11 22 33 44"
::"数组list[44]=11 22 33 44"
echo %list[1]%	:: 这种访问方法是错误的
```

### 迭代数组 for /l

```bat
:: 迭代数组
@echo off
setlocal enabledelayedexpansion ::启动延迟扩展(虽然::后边的类容不能识别，但不影响::前面功能的实现)
:: 数组中的每个元素都需要使用`set`命令专门定义
set topic[0]=comments 		
set topic[1]=variables 
set topic[2]=Arrays 
set topic[3]=Decision making 
set topic[4]=Time and date 
set topic[5]=Operators 

:: 语法：for /l %%variable in (start,step,end) do command
:: !topic[%%n]! 使用了延迟环境变量扩展，! 符号用于括起延迟扩展的变量。
for /l %%n in (0,1,5) do (	:: (可以在此处备注而不影响功能,下边一行不能备注)
   echo !topic[%%n]!		
)
endlocal

Comments 
variables 
Arrays 
Decision making 
Time and date 
Operators
```

### 数组长度 : if defind

```bat
:: if defined 在处理数组时通常用于检查数组中特定索引的元素是否
:: 数组长度
set Arr[0]=1 
set Arr[1]=2 
set Arr[2]=3 
set Arr[3]=4 

set "x=0"
:SymLoop
if defined Arr[%x%] (
	:: call用于调用另一个批处理命令并传递控制权
	call echo %%Arr[%x%]%% 	
	set /a "x+=1"
	GOTO :SymLoop 	
)
echo "The length of the array is" %x%
The length of the array is 4
```

```bat
set "ArrayLength=0"
set "Index=0"
:Loop
if defined Arr[%Index%] (
    set /a "ArrayLength+=1"
)
set /a "Index+=1"
if defined Arr[%Index%] (
    goto :Loop
)
echo Array Length: %ArrayLength%
```

在没有显式初始化数组的情况下，如果你尝试访问数组中不存在的索引，会导致错误。使用 `if defined` 可以在访问数组之前进行检查，以避免出现未定义的数组元素，从而增强脚本的健壮性。

在上面的代码中，使用双引号来包含变量赋值语句是为了避免潜在的问题，尤其在涉及带有空格或特殊字符的变量值时。
使用双引号来包含变量赋值语句好处：

1. 处理带有空格的变量值：如果变量值包含空格，如果不使用双引号，批处理会将空格解释为参数的分隔符。使用双引号可以确保整个变量值被视为一个单独的字符串。
2. 避免意外解析：使用双引号可以防止特殊字符（例如 `&`、`<`、`>` 等）在赋值过程中被意外解析，从而避免潜在的问题。
3. 更好的代码可读性：添加双引号可以使代码更清晰易读，特别是在赋值语句较长或复杂的情况下。

在上面的代码中，设置变量 `ArrayLength` 和 `Index` 的值时，因为变量值通常不包含空格或特殊字符，所以使用双引号并不是必需的，不加引号也可以工作。

### call

`call` 命令在批处理脚本中有多种用途，除了上述示例中用于**调用另一个批处理命令并传递控制权外**，还可以用于其他情况：

1. 调用**其他批处理文件**：使用 `call` 命令可以在当前批处理文件中调用其他批处理文件。例如：`call other_script.bat`。

2. 调用**标签（子程序）**：在批处理中，可以使用 `call :label` 来调用定义在同一个批处理文件中的标签（子程序），然后返回到原来的位置。这样可以实现函数的效果。

   ```bat
   @echo off
   
   call :myFunction	:: 执行完myFunction后，回到这个位置
   echo Back to the main script
   goto :EOF
   
   :myFunction
   echo This is my function.
   goto :EOF
   ```

   ```
   This is my function.
   Back to the main script
   ```

3. 调用**系统命令**：`call` 命令还可以用于调用系统命令或其他可执行文件。例如，你可以使用 `call dir` 来执行 `dir` 命令来列出当前目录的文件。

4. 调用**其他命令处理器**：在某些情况下，你可能需要在批处理文件中调用其他命令处理器，例如 PowerShell 或 Python。使用 `call` 命令可以启动其他命令处理器，并执行特定的命令。

**注意**：使用 `call` 命令时，如果在被调用的脚本或命令处理器执行完毕后，控制权会返回到调用的位置。
如果不使用 `call` 命令而直接执行外部脚本或命令处理器，它们执行完毕后，不会返回到原来的脚本位置，而是直接结束批处理。
因此，在需要返回到原来位置的情况下，应该使用 `call` 命令。

### 在数组中创建结构 ?

结构也可以在批处理文件中使用一点额外的编码来实现。 

```bat
@echo off 
set len=3 
set obj[0].Name=Joe 
set obj[0].ID=1 
set obj[1].Name=Mark 
set obj[1].ID=2 
set obj[2].Name=Mohan 
set obj[2].ID=3 

set i=0 
:loop 
if %i% equ %len% goto :eof 
set cur.Name= 
set cur.ID=

for /f "usebackq delims==.tokens=1-3" %%j in (`set obj[%i%]`) do ( 
   set cur.%%k=%%l 
) 
echo Name=%cur.Name% 
echo Value=%cur.ID% 
set /a i=%i%+1 
goto loop
Bat
```

- 使用`set`命令定义的每个变量具有与数组的每个索引关联的`2`个值。
- 变量`i`设置为`0`，以便可以遍历结构将数组的长度为`3`。
- 总是检查`i`的值是否等于`len`的值，如果不是，则循环遍历代码。
- 可以使用`obj[%i%]`表示法访问结构的每个元素。

```shell
Name=Joe 
Value=1 
Name=Mark 
Value=2 
Name=Mohan 
Value=3
```



---

## 决策结构 if

决策结构要求程序员指定一个或多个要由程序进行评估或测试的条件，以及如果条件被确定为`True`，则执行的语句或语句，以及可选地，如果 条件被确定为`False`。

| 编号 | 条件结构                                                     | 描述                               |
| ---- | ------------------------------------------------------------ | ---------------------------------- |
| 1    | [if语句](http://www.yiibai.com/batch_script/batch_script_if_statement.html) | 第一个决策语句是`if`语句。         |
| 2    | [if/else语句](http://www.yiibai.com/batch_script/batch_script_if_else_statement.html) | 下一个决策语句是`if/else`语句。    |
| 3    | [嵌套if语句](http://www.yiibai.com/batch_script/batch_script_nested_if_statements.html) | 有时候，要求有多个嵌套的`if`语句。 |

### if defind 变量定义检测

```bat
:: 语法：if defined somevariable somecommand 用于测试变量是否存在。
@echo off 
SET str1=String1 
SET str2=String2 
if defined str1 echo "Variable str1 is defined"		:: bat的结构视乎没有TCL的结构要求高
if defined str3 (
	echo "Variable str3 is defined"
) else (
	echo "Variable str3 is not defined"
)
```

```bat
"Variable str1 is defined" 
"Variable str3 is not defined"
```

### if exists 文件检测

```bat
:: 语法：If exist somefile.ext do_something 用于测试文件是否存在
@echo off 
if exist C:\set2.txt echo "File exists" 
if not exist C:\set3.txt (echo "File not exists")
else (echo "File does not exist")
```

假设在C驱动器中有一个名为`set2.txt`的文件，并且没有名为`set3.txt`的文件。 

```shell
"File exists"
"File does not exist"
```

### if errorlevel

用于测试运行的最后一个命令的退出代码。 
各种命令发出整数退出代码来表示命令的状态。 
通常，如果命令成功完成，则命令通过传递`0`;如果命令失败，命令通过传递`1`。

```bat
if errorlevel n somecommand
```

其中`“n”`是整数退出码之一。

### goto语句

一般来说，批处理文件的执行是逐行进行的，每行依次运行命令。 但是，通常希望在跳过其他部分的同时执行批处理文件的特定部分。 跳转到特定部分的能力由`“goto”`命令(写成一个字)提供。 目标部分在开头用带冒号的名称标注。

```shell
:: 为什么这是一个 shell语句
... 
goto :label 
...some commands 
:label 
...some other commands
```

执行将跳过“一些命令”，并开始“其他一些命令”。 标签可以是脚本中任何地方的一行，包括在`“goto”`命令之前。`“if”`语句中经常出现`“goto”`命令。 

```bat
:: 语法：if (condition) goto :label
@echo off 
SET /A a=5 

if %a%==5 goto :labela 
if %a%==10 goto :labelb

:labela 
echo "The value of a is 5" 

exit /b 0

:labelb 
echo "The value of a is 10"
```

```shell
"The value of a is 5"
```

`exit /b 0` 是用于退出当前的批处理脚本的命令。

1. `exit`：这个命令用于退出当前的批处理脚本。
2. `/b`：这是 `exit` 命令的一个参数，它表示在退出时返回一个错误级别（exit code）给操作系统。
   在这里，`/b 0` 表示在退出时返回错误级别为 0。

错误级别是一个整数值，用于表示上一个命令或程序的执行结果状态。
在批处理脚本中，通常将错误级别用于条件判断或者表示脚本执行的成功与否。

使用 `exit /b 0` 表示脚本执行成功，并返回错误级别为 0。一般来说，错误级别为 0 表示没有错误，脚本执行成功。

在这个脚本中，当变量 `a` 的值为 5 时，脚本会跳转到 `:labela` 标签处，并输出 `"The value of a is 5"`。然后，执行 `exit /b 0` 表示脚本执行成功，并返回错误级别 0。

如果变量 `a` 的值不是 5，那么脚本会继续执行，不会跳转到 `:labela` 标签，也不会执行 `exit /b 0` 命令，脚本会继续执行后面的代码。

**总结：**

- `exit` 命令用于退出当前的批处理脚本。**并指定了一个退出状态。**
- `exit /b` 可以附加一个错误级别，用于表示脚本执行的状态，`/b 0` 表示脚本执行成功，返回错误级别为 0。



---

## 运算符

### 关系运算符

关系运算符允许对象的比较

| 运算符 | 描述 |  示例   |
| :----: | :--- | :-----: |
|  EQU   | ==   | 2 EQU 2 |
|  NEQ   | ！=  | 3 NEQ 2 |
|  LSS   | <    | 2 LSS 3 |
|  LEQ   | <=   |  LEQ 3  |
|  GTR   | >    | 3 GTR 2 |
|  GEQ   | >=   | 3 GEQ 2 |

### 逻辑运算符

| 运算符 |        描述        |
| :----: | :----------------: |
|  AND   | 这是逻辑"和"运算符 |
|   OR   | 这是逻辑"或"运算符 |
|  NOT   | 这是逻辑"非"运算符 |

```bat
@echo off
SET /A a=5
SET /A b=10
IF %a% LSS 10 (
	IF %b% GTR 0 (
		ECHO %a% is less than 10 AND %b% is greater than 0
	)
) 
5 is less than 10 AND 10 is greater than 0
```

```bat
SET /A a=5
SET /A b=10
IF %a% GEQ 10 (
   IF %b% LEQ 0 (
      ECHO %a% is NOT less than 10 OR %b% is NOT greater than 0
   ) ELSE (
      ECHO %a% is less than 10 OR %b% is greater than 0
   )
) ELSE (
   ECHO %a% is less than 10 OR %b% is greater than 0
)
5 is less than 10 AND 10 is greater than 0
```

```bat
SET /A a=5
IF NOT %a%==6 echo "A is not equal to 6"
"A is equal to 5"
```

### 赋值运算符

| 运算符 |                         描述                         |             示例             |
| :----: | :--------------------------------------------------: | :--------------------------: |
|  + =   |    这会向左操作数添加右操作数并将结果赋给左操作数    |  设置/A a=5  a+ = 3输出为8   |
|  -  =  | 这会从左操作数中减去右操作数并将结果分配给左边操作数 | 设置/A a=5  a  -  = 3输出为2 |
|  * =   |    这将右操作数与左操作数相乘并指定结果到左操作数    | 设置/A a=5  a * = 3输出为15  |
|   /=   |    这将左操作数除以右操作数，并将结果赋给左操作数    |   设置/A a=6  a/= 3输出为2   |
|  ％=   |     这使用两个操作数获取模数并将结果赋给左操作数     |  设置/A  =5  a％= 3输出为2   |

```bat
set a=0
set /a delay=!delay!+1
set /a delay+=2
```



### 按位运算符

按位运算符也可以在批处理脚本中使用。 以下是可用的运算符。

- `&` - 这是按位“和”运算符
- `|` - 这是按位“或”运算符
- `^` - 这是按位“异或”或“独占”或操作符



---

## 日期和时间 date time ?

```bat
echo %date%		:: 2018/01/24 周三
echo %time%		:: 21:16:52.81
```

```bat
@echo off 
echo/Today is: %year%-%month%-%day% 

goto :EOF 
setlocal ENABLEEXTENSIONS 
set t=2&if "%date%z" LSS "A" set t=1 

for /f "skip=1 tokens=2-4 delims=(-)" %%a in ('echo/^|date') do ( 
   for /f "tokens=%t%-4 delims=.-/ " %%d in ('date/t') do ( 
      set %%a=%%d&set %%b=%%e&set %%c=%%f)) 
endlocal&set %1=%yy%&set %2=%mm%&set %3=%dd%&goto :EOF

Today is: 2017-12-30
```



---

## 输入输出 ?

有三个键盘输入的通用“文件”，在屏幕上打印文本和在屏幕上打印错误。

-  标准输入文件(**stdin**)包含程序/脚本的输入。
-  标准输出(Standard Out)文件(**stdout**)被用来写输出以显示在屏幕上。 
- 标准错误(**stderr**)文件包含用于显示在屏幕上的任何错误消息。

这三个标准文件中的每一个(也称为标准流)分别使用数字`0`,`1`和`2`进行引用。
Stdin是文件`0`，stdout是文件`1`，stderr是文件`2`。

### 重定向输出(Stdout和Stderr)

批处理文件中的一种常见做法是**将程序的输出发送到日志文件**。
 `>`运算符将stdout或stderr发送或重定向到另一个文件。 

```bat
:: 命令`dir C:\` 的stdout被重定向到文件`list.txt`
dir C:\  > list.txt
```

```bat
:: 如果将数字`2`附加到重定向过滤器，则会将stderr重定向到文件`lists.txt`
dir C:\ 2 > list.txt
```

```bat
:: 使用文件编号和`"&"`前缀来组合stdout和stderr流。 
dir C:\ > lists.txt 2> &1
```

### 抑制程序输出 NUL

**伪文件`NUL`用于丢弃程序的任何输出。**

```bat
:: 使用文件编号和`"&"`前缀来组合stdout和stderr流
Dir C:\ > NUL
```

**STDIN**

要使用Stdin，必须使用解决方法来实现此目的。这可以通过重定向命令提示符自己的标准输入(称为`CON`)来完成。

以下示例显示了如何将输出重定向到名为`lists.txt`的文件。 在执行下面的命令后，命令提示符会将用户输入的所有输入都保存到一个`EOF`字符中。 稍后，它将所有输入发送到文件`lists.txt`。

```bat
TYPE CON > lists.txt
```



---

## 函数 :

函数是组织在一起执行特定任务的一组语句。 

像其他语言一样，批处理脚本中的函数也遵循相同的程序规则 -

- **函数声明** - 它告诉编译器一个函数的名字，返回类型和参数。
- **函数定义** - 它提供了函数的实际主体。

### 函数定义

在批处理脚本中，通过使用标签语句来定义函数。 当一个函数被重新定义时，它可能会将一个或多个值作为函数的输入“参数”，并在函数的主体中处理，并将值作为输出“返回类型”传回给函数。

每个函数都有一个函数名称，它描述了函数执行的任务。 要使用一个函数，需要用它的名称来“调用”这个函数，并传递与函数参数类型相匹配的输入值(称为参数)。

```bat
:function_name 
	Do_something 
EXIT /B 0		:: `EXIT`语句用于确保函数正常退出，/B 0 返回错误级别
```

### 调用

```bat
call :function_name
Call :function_name parameter1, parameter2… parametern
```

定义主程序时需要注意的一点是确保在主程序中放入`EXIT / B%ERRORLEVEL%`语句，以便将主程序的代码与函数分开。

通过使用代字符(`~`)字符以及参数的位置，来在函数内部访问参数。

```bat
@echo off
SETLOCAL
CALL :Display 5 , 10
EXIT /B %ERRORLEVEL%
:Display
	echo The value of parameter 1 is %~1
	echo The value of parameter 2 is %~2
EXIT /B 0
```

```
The value of parameter 1 is 5
The value of parameter 2 is 10
```

### **使用返回值调用函数**

使用`set`命令和代字号(`~`)字符以及参数的位置编号在函数中设置返回值。

```bat
@echo off
SETLOCAL
CALL :SetValue value1,value2
	echo %value1%
	echo %value2%
EXIT /B %ERRORLEVEL%
:SetValue
	set "%~1=5"
	set "%~2=10"
EXIT /B 0
```

### 函数中的局部变量

函数中的局部变量可以用来**避免名称冲突**，并**保持函数本地的变量变化**。 `SETLOCAL`命令首先用于确保命令处理器对所有环境变量进行备份。 通过调用`ENDLOCAL`命令可以恢复变量。 在两者之间进行的更改是当前批处理脚本的本地处理。 当到达批处理文件结束时，即通过调用`GOTO：EOF`，`ENDLOCAL`被自动调用。

使用`SETLOCAL`对变量进行本地化允许在函数中自由使用变量名称，而不必担心与函数外使用的变量的名称冲突。

以下示例显示了如何在函数中使用局部变量。

```bat
::使用ANSI编码
@echo off
REM 函数调用
echo.
echo --------------------函数调用-----
call :myFunction val1,val2,val3

REM 函数执行完成回到主函数，实参的变量值不丢失
echo.
echo --------------------子函数执行完成回到主函数，实参的变量值不丢失-----
echo 子函数的形参val2 = %val2%
echo 子函数的形参val1 = %val1%

REM exit /B %ERRORLEVEL%
echo.
echo --------------------按任意键退出cmd
pause	
exit /B 1	::结束主函数


REM 子函数，实参只有在第一次赋值是需要使用%~<实参序号>
:myFunction
echo ------------------------------正在执行子函数-----
	set	str=666
	set	"%~2=2"
	set %~3=%str%
	setlocal
		echo 子函数的形参val3 = %val3%
		set	str=888
		set %~3=%str%
		echo 子函数的形参val3 = %val3%
		::局部只能在
	endlocal
	echo 子函数的形参val3 = %val3%
	echo 子函数的形参val2 = %val2%
	echo 子函数的形参val1 = %~1
	echo 按任意键结束子函数回到主函数
	REM pause
REM goto myFunction ::在次返回这个函数

::--------------------函数调用-----
::------------------------------正在执行子函数-----
::子函数的形参val3 = 666
::子函数的形参val3 = 888
::子函数的形参val3 = 666
::子函数的形参val2 = 2
::子函数的形参val1 = val1
::按任意键结束子函数回到主函数
::
::--------------------子函数执行完成回到主函数，实参的变量值不丢失-----
::子函数的形参val2 = 2
::子函数的形参val1 =
::
::--------------------按任意键退出cmd
::请按任意键继续. . .

```

**在上面的程序中，变量`str`被定位在函数`SetValue`中。 因此，即使`str`值被返回到`main`函数，`main`函数中`str`的值也不会被函数返回的值替换。**

```bat
Outer
Outer
```

### 函数递归 ？

通过在函数中保持局部变量的变化并且对调用者不可见，完全封装函数主体的能力。
我们现在可以递归地调用一个函数，确保每个级别的递归都可以使用自己的一组变量，即使变量名被重用。

这个例子展示了如何递归地计算一个斐波那契数。 当斐波那契算法达到一个大于或等于给定输入数的数时，递归停止。 该示例以数字`0`和`1`开头，`myFibo`函数递归调用以计算下一个斐波那契数，直到找到斐波那契数大于或等于`1000000000`。

`myFibo`函数的第一个参数是要存储输出的变量的名称。该变量必须初始化为以开始的斐波那契数，并将在调用该函数时用作当前斐波那契数，并设置为后续函数的斐波那契数。

```bat
@echo off
set "fst=0"
set "fib=1"
set "limit=1000000000"
call:myFibo fib,%fst%,%limit%
	echo.The next Fibonacci number greater or equal %limit% is %fib%.
	echo.&pause&goto:eof
:myFibo -- calculate recursively
:myFibo -- calculate recursively the next Fibonacci number greater or equal to a limit
	SETLOCAL
		set /a "Number1=%~1"
		set /a "Number2=%~2"
		set /a "Limit=%~3"
		set /a "NumberN=Number1 + Number2"
		
if /i %NumberN% LSS %Limit% call:myFibo NumberN,%Number1%,%Limit%
(ENDLOCAL
   IF "%~1" NEQ "" SET "%~1=%NumberN%"
)goto:eof
```

```bat
The next Fibonacci number greater or equal 1000000000 is 1134903170.
```



---

## 进程

### 1. 查看正在运行的进程列表 tasklist

在批处理脚本中，可以使用`TASKLIST`命令来获取系统中当前正在运行的进程的列表。

```bat
TASKLIST [/S system [/U username [/P [password]]]] [/M [module] | /SVC | /V] [/FI filter]
[/FO format] [/NH]
```

- `*/S system* - 指定要连接的远程系统。`
- `*/U [domain]user* - 指定命令应在其下执行的用户上下文。`
- `*/P [password]* - 指定给定用户上下文的密码。 提示输入，如果省略。`
- `*/M [module]* - 列出当前使用给定的exe / dll名称的所有任务。 如果未指定模块名称，则显示所有已加载的模块。`
- `*/SVC* - 显示每个进程中托管的服务。`
- `*/V* - 显示详细的任务信息。`
- `*/FI filter* - 显示一组符合过滤器指定条件的任务。`
- `*/FO format* - 指定输出格式。 有效值:TABLE，LIST，CSV。`
- `*/NH* - 指定“列标题”不应显示在输出中。 仅适用于TABLE和CSV格式。`

```bat
:: 获得本地系统上运行的所有进程的列表
tasklist

rem 显示一系列符合筛选器指定条件的任务。
:: 只能获取内存大于`40MB`的进程
tasklist /fi "memusage gt 40000"
:: 将`tasklist`命令的输出显示保存到`process.txt`文件中。
tasklist > process.txt
```

```shell
映像名称                       PID 会话名              会话#       内存使用 
========================= ======== ================ =========== ============
System Idle Process              0 Services                   0          8 K
System                           4 Services                   0        136 K
```



### 2. 杀死/终止一个进程 tsskill

允许运行Microsoft Windows XP Professional，Windows 2003或更高版本的用户通过进程ID(PID)或映像名称从Windows命令行中终止任务。 杀死/终止一个进程的命令是`TASKILL`命令。

```bat
taskkill [/S system [/U username [/P [password]]]] { [/FI filter] 
[/PID processid | /IM imagename] } [/T] [/F]
```

- `*/S system* - 指定要连接的远程系统`
- `*/U [domain]user* - 指定命令应在其下执行的用户上下文。`
- `*/P [password]* - 指定给定用户上下文的密码。 提示输入，如果省略。`
- `*/FI FilterName* - 应用过滤器来选择一组任务，允许使用*通配符。`
- `*/PID processID* - 指定要终止的进程的PID。使用TaskList来获取PID。`
- `*/IM ImageName* - 指定要终止的进程的映像名称。 通配符*可用于指定所有任务或图像名称。`
- `*/T* - 终止指定的进程以及由其启动的任何子进程。`
- `*/F* - 指定强制终止进程。`

```bat
:: 如果打开记事本，这个命令将杀死(终止)打开的记事本任务
taskkill /f /im notepad.exe
```

```bat
:: 杀死了一个ID为`9901`的进程
taskill /pid 9901
```

### 3. 启动一个新的过程 start

DOS脚本也可以完全启动一个新的进程。这是通过使用`START`命令来实现的。

```bat
START "title" [/D path] [options] "command" [parameters]
```

- *title* - CMD窗口标题栏的文本(必需)
- *path* - 起始目录。
- *command* - 命令，批处理文件或可执行程序运行。
- *parameters* - 传递给命令的参数。

以下是`START`命令的选项的描述。

- */MIN* - 启动窗口最小化。
- */MAX* - 启动窗口最大化。
- */LOW* - 使用`IDLE`优先级。
- */NORMAL* - 使用`NORMAL`优先级。
- */ABOVENORMAL* - 使用`ABOVENORMAL`优先级。
- */BELOWNORMAL* - 使用`BELOWNORMAL`优先级。
- */HIGH* - 使用`HIGH`优先级。
- */REALTIME* - 使用`REALTIME`优先级。

**示例**

```bat
START "Test Batch Script" /Min test.bat
```

上述命令将在新窗口中运行批处理脚本`test.bat`。 窗口将以最小化模式启动，并且指定标题为:*“Test Batch Script”*。

```bat
START "" "C:\Program Files\Microsoft Office\Winword.exe" "D:\test\TESTA.txt"
```

上述命令实际上将在另一个进程中运行`Microsoft Word`，然后在MS Word中打开文件`TESTA.txt`。



---

## 批处理别名

别名表示现有命令创建快捷键或关键字。 假设想要执行下面的命令，不是使用`/w`选项的目录列表命令，而不是在目录列表中显示所有必要的细节。

```bat
dir /w
```

假设如果要创建这个命令的**快捷方式**如下。

```bat
dw=dir /w
```

当要执行`dir /w`命令时，可以简单地键入`dw`这个单词。`dw`这个词现在已经成为命令`dir /w`的别名。

### 创建别名

别名通过使用`doskey`命令进行管理。

```bat
doskey [options] [macroname=[text]]
```

- *macroname* - 宏的简称。
- *text* - 要调用的命令。

`DOSKEY`命令的选项的说明

| 编号 | 选项                    | 描述                                             |
| ---- | ----------------------- | ------------------------------------------------ |
| 1    | `/REINSTALL`            | 安装Doskey的新副本                               |
| 2    | `/LISTSIZE = size`      | 设置命令历史缓冲区的大小。                       |
| 3    | `/MACROS`               | 显示所有Doskey宏。                               |
| 4    | `/MACROS:ALL`           | 显示所有具有Doskey宏的可执行文件的所有Doskey宏。 |
| 5    | `/MACROS:exename`       | 显示给定可执行文件的所有Doskey宏。               |
| 6    | `/HISTORY`              | 显示存储在内存中的所有命令。                     |
| 7    | `/INSERT`               | 指定键入的新文本以旧文本插入。                   |
| 8    | `/OVERSTRIKE`           | 指定新文本覆盖旧文本。                           |
| 9    | `/EXENAME = exename`    | 指定可执行文件。                                 |
| 10   | `/MACROFILE = filename` | 指定要安装的宏的文件。                           |
| 11   | `macroname`             | 指定创建的宏的名称。                             |
| 12   | `text`                  | 指定要录制的命令。                               |

```bat
@echo off
doskey cd=cd/test	:: 自动进入名为`test`的目录
doskey d=dir
```

当执行该命令，就可以在命令提示符下运行这些别名。

下面的截图显示了在上面创建的批处理文件被执行后，可以自由地输入`d`命令，它会给目录列表，这意味着别名已经被创建成功了。
![img](https://gitee.com/jiagnkun/procotol_device/raw/master/Typora/DaLei/assic.picture/202308021946578.jpeg)

### 删除别名

通过将宏的值设置为`NULL`，可以删除别名或宏。

```bat
:: 首先将宏`d`设置为`d = dir`。 之后将其设置为`NULL`。所以宏`d`将被删除。
@echo off
doskey cd=cd/test
doskey d=dir
doskey d=null

::/d-管理别名和宏（语法：doskey /d:<别名>；来自chatgtp）
```

### 替换别名

可以通过将宏的值设置为新的期望值来替换别名或宏。

```bat
@echo off
doskey cd=cd/test
doskey d=dir

d=dir /w
```



---

## 批处理设备

Windows现在有一个改进的库，可以在批处理脚本中使用，以处理连接到系统的设备。 这就是所谓的设备控制台 - `DevCon.exe`。

Windows驱动程序开发人员和测试人员可以使用`DevCon`来验证是否正确安装并配置了驱动程序，包括正确的INF文件，驱动程序堆栈，驱动程序文件和驱动程序包。 也可以在脚本中使用DevCon命令(启用，禁用，安装，启动，停止和继续)来测试驱动程序。 DevCon是一个在本地计算机和远程计算机上执行设备管理功能的命令行工具。

显示驱动程序和设备信息DevCon可以显示本地计算机和远程计算机(运行Windows XP及更早版本)上的驱动程序和设备的以下属性 -

- 硬件ID，兼容的ID和设备实例ID。 这些标识符在设备标识字符串中有详细的描述。
- 设备设置类。
- 设备设置类中的设备。
- INF文件和设备驱动程序文件。
- 驱动程序包的细节。
- 硬件资源。
- 设备状态。
- 预期的驱动程序堆栈。
- 驱动程序商店中的第三方驱动程序包。
- 搜索设备DevCon可以通过硬件ID，设备实例ID或设备设置类在本地或远程计算机上搜索已安装和未安装的设备。
- 更改设备设置DevCon可以通过以下方式更改本地计算机上即插即用(PnP)设备的状态或配置 -
  - 启用设备。
  - 禁用设备。
  - 更新驱动程序(交互式和非交互式)。
  - 安装一个设备(创建一个devnode并安装软件)。
  - 从设备树中删除设备并删除设备堆栈。
  - 重新扫描即插即用设备。
  - 添加，删除和重新排序根枚举设备的硬件ID。
  - 更改设备设置类的上部和下部过滤器驱动程序。
  - 从驱动程序存储添加和删除第三方驱动程序包。

DevCon(DevCon.exe)包含在为桌面应用程序安装WDK，Visual Studio和Windows SDK时。 `DevCon.exe`工具包在安装时位于以下位置。

```bat
%WindowsSdkDir%\tools\x64\devcon.exe
%WindowsSdkDir%\tools\x86\devcon.exe
%WindowsSdkDir%\tools\arm\devcon.exe
```

**语法**

```bat
devcon [/m:\\computer] [/r] command [arguments]
```

其中，

- `/m:\\computer` - 在指定的远程计算机上运行该命令。 反斜杠是必需的。
- `/r` - 有条件的重启。 只有在需要重新启动以使更改生效时，才能在完成操作后重新启动系统。
- `command` - 指定一个DevCon命令。
- 要列出并显示计算机上的设备信息，请使用以下命令 -
  - *DevCon HwIDs*
  - *DevCon Classes*
  - *DevCon ListClass*
  - *DevCon DriverFiles*
  - *DevCon DriverNodes*
  - *DevCon Resources*
  - *DevCon Stack*
  - *DevCon Status*
  - *DevCon Dp_enum*
- 要搜索有关计算机上设备的信息，请使用以下命令 -
  - *DevCon Find*
  - *DevCon FindAll*
- 要操纵设备或更改其配置，请使用以下命令 -
  - DevCon Enable
  - DevCon Disable
  - DevCon Update
  - DevCon UpdateNI
  - DevCon Install
  - DevCon Remove
  - DevCon Rescan
  - DevCon Restart
  - DevCon Reboot
  - DevCon SetHwID
  - DevCon ClassFilter
  - DevCon Dp_add
  - DevCon Dp_delete

**例子**
以下是关于如何使用DevCon命令的一些示例。  

```bat
List all driver files
```

以下命令使用DevCon DriverFiles操作来列出系统上的设备使用的驱动程序的文件名。 该命令使用通配符(`*`)来指示系统中的所有设备。 由于输出很广泛，因此该命令使用重定向字符(`>`)将输出重定向到参考文件`driverfiles.txt`。

```bat
devcon driverfiles * > driverfiles.txt
```

以下命令使用DevCon状态操作来查找本地计算机上所有设备的状态。 然后将状态保存在`status.txt`文件中以供日志记录或以后查看。 该命令使用通配符(`*`)表示所有设备，并使用重定向字符(`>`)将输出重定向到`status.txt`文件。

```bat
devcon status * > status.txt
```

以下命令通过在`DevCon Enable`命令中指定`Printer Setup`类来启用计算机上的所有打印机设备。 该命令包含`/r`参数，如果需要使系统有效，则重新引导系统。

```bat
devcon /r enable=Printer
```

以下命令使用DevCon安装操作在本地计算机上安装键盘设备。 该命令包含设备的INF文件(`keyboard.inf`)和硬件ID(`* PNP030b`)的完整路径。

```bat
devcon /r install c:\windows\inf\keyboard.inf *PNP030b
Bat
```

以下命令将扫描计算机中的新设备。

```bat
devcon scan
```

以下命令将重新扫描新设备的计算机。

```bat
devcon rescan
```



---

## 批处理注册表

注册表是Windows系统的关键要素之一。 它包含有关操作系统各个方面的大量信息。 几乎所有安装在Windows系统上的应用程序都以某种形式与注册表交互。

注册表包含两个基本元素:键和值。 注册表项是与文件夹类似的容器对象。 注册表值是与文件类似的非容器对象。键可能包含值或其他键。 使用类似于Windows路径名称的语法来引用键，并使用反斜杠来指示层次结构的级别。

本章介绍查询值，添加，删除和编辑注册表中的值等各种功能。

| 编号 | 注册表的类型                                                 | 描述                                        |
| ---- | ------------------------------------------------------------ | ------------------------------------------- |
| 1    | [从注册表中读取](http://www.yiibai.com/batch_script/batch_script_reading_registry.html) | 从注册表中读取是通过`REG QUERY`命令完成的。 |
| 2    | [添加到注册表中](http://www.yiibai.com/batch_script/batch_script_adding_registry.html) | 添加到注册表是通过`REG ADD`命令完成的。     |
| 3    | [从注册表中删除](http://www.yiibai.com/batch_script/batch_script_deleting_registry.html) | 从注册表中删除是通过`REG DEL`命令完成的。   |
| 4    | [复制注册表项](http://www.yiibai.com/batch_script/batch_script_copying_registry_keys.html) | 从注册表复制是通过`REG COPY`命令完成的。    |
| 5    | [比较注册表项](http://www.yiibai.com/batch_script/batch_script_comparing_registry_keys.html) | 比较注册表项是通过`REG COMPARE`命令完成的。 |

//更多请阅读：https://www.yiibai.com/batch_script/batch_script_registry.html#article-start 



---

## 批处理网络设置

批处理脚本可以使用网络设置。 `NET`命令用于更新，修复或查看网络或网络设置。 本章介绍`net`命令可用的不同选项。

| 编号 | 命令                                                         | 描述                                             |
| ---- | ------------------------------------------------------------ | ------------------------------------------------ |
| 1    | [NET ACCOUNTS](http://www.yiibai.com/batch_script/batch_script_net_accounts.html) | 查看计算机的当前密码和登录限制。                 |
| 2    | [NET CONFIG](http://www.yiibai.com/batch_script/batch_script_net_config.html) | 显示当前的服务器或工作组设置。                   |
| 3    | [NET COMPUTER](http://www.yiibai.com/batch_script/batch_script_net_computer.html) | 添加或删除附加到Windows域控制器的计算机。        |
| 4    | [NET USER](http://www.yiibai.com/batch_script/batch_script_net_user.html) | 该命令可以用于查看特定用户帐户的详细信息。       |
| 5    | [NET STOP/START](http://www.yiibai.com/batch_script/batch_script_net_stop_start.html) | 该命令用于停止和启动特定的服务。                 |
| 6    | [NET STATISTICS](http://www.yiibai.com/batch_script/batch_script_net_statistics.html) | 显示工作站或服务器的网络统计信息。               |
| 7    | [NET USE](http://www.yiibai.com/batch_script/batch_script_net_use.html) | 连接或断开计算机与共享资源或显示有关连接的信息。 |

//更多请阅读：https://www.yiibai.com/batch_script/batch_script_network.html#article-start 



---

## 批处理打印

也可以通过`NET PRINT`命令从批处理脚本中控制打印。

**语法**

```bat
PRINT [/D:device] [[drive:][path]filename[...]]
```

其中，`/D:device` - 指定打印设备。

**示例**

```bat
print c:\example.txt /c /d:lpt1
```

上述命令将打印`example.txt`文件到并行端口`lpt1`。

### 命令行打印机控制

从Windows 2000开始，可以使用`PRINTUI.DLL`和`RUNDLL32.EXE`从Windows的命令行配置许多但不是全部的打印机设置

**语法**

```bat
RUNDLL32.EXE PRINTUI.DLL,PrintUIEntry [ options ] [ @commandfile ]
```

有一些可用的选项是以下 -

- */dl* - 删除本地打印机。
- */dn* - 删除网络打印机连接。
- */dd* - 删除打印机驱动。
- */e* - 显示打印首选项。
- */f[file]* - `inf`文件或输出文件。
- */F[file]*  - INF文件使用`/f`指定的INF文件的位置。
- */ia* - 使用`inf`文件安装打印机驱动程序。
- */id* - 使用添加打印机驱动程序向导安装打印机。
- */if* - 使用`inf`文件安装打印机。
- */ii* - 使用添加打印机向导与`inf`文件安装打印机。
- */il* - 用添加打印机向导安装打印机。
- */ip* - 使用网络打印机安装向导安装打印机。
- */k* - 将测试页打印到指定的打印机，安装打印机时不能与命令组合。
- */l[path]* - 打印机驱动程序源路径。
- */m[model]* - 打印机驱动程序型号名称。
- */n[name]* - 打印机名称。
- */o* - 显示打印机队列视图。
- */p* - 显示打印机属性。
- */Ss* - 将打印机设置存储到文件中。
- */Sr* - 从文件恢复打印机设置。
- */y* - 将打印机设置为默认值。
- */Xg* - 获取打印机设置。
- */Xs* - 设置打印机设置。

### 测试打印机是否存在

有些情况下，可能会连接到网络打印机而不是本地打印机。 在这种情况下，在打印之前首先检查打印机是否存在是很有必要的。

可以使用`RUNDLL32.EXE PRINTUI.DLL`来评估打印机的存在，该文件用于控制大部分的打印机设置。

**示例**

```bat
SET PrinterName=Test Printer
SET file=%TEMP%\Prt.txt
RUNDLL32.EXE PRINTUI.DLL,PrintUIEntry /Xg /n "%PrinterName%" /f "%file%" /q

IF EXIST "%file%" (
   ECHO %PrinterName% printer exists
) ELSE (
   ECHO %PrinterName% printer does NOT exists
)
```

上面的命令将执行以下操作 -

- 它将首先设置打印机名称并设置将保存打印机设置的文件名。
- `RUNDLL32.EXE PRINTUI.DLL`命令将用于通过将文件的配置设置发送到文件`Prt.txt`来检查打印机是否存在。



---

## 批处理脚本调试

通常情况下，运行批处理文件时可能会遇到问题，而且大多数情况下都需要以某种方式调试批处理文件，以确定是批处理文件本身的问题。 以下是一些可以帮助调试批处理脚本文件的技术。

### 错误消息

要找出消息的来源，请按照下列步骤操作 - 

**第1步** - 移除`REM @ECHO OFF`，即`REM @ECHO OFF`或`:: @ECHO OFF`。
**第2步** - 使用必要的命令行参数运行批处理文件，将所有输出重定向到日志文件以供以后比较。

```bat
test.bat > batch.log 2>&1
```

**第3步** - 在文件`batch.log`中搜索错误消息

**第4步** - 检查上一行是否有任何意外或无效的命令，命令行开关或值; 要特别注意命令中使用的任何环境变量的值。

**第5步** - 纠正错误并重复此过程，直到所有错误消息都消失。

### 复杂的命令行

另一个常见的错误来源是不正确的重定向命令，例如，使用不正确的搜索字符串“嵌套” `FIND`或`FINDSTR`命令，有时在`FOR / F`循环中。

要检查这些复杂命令的有效性，请按照下列步骤操作 -

**第1步** - 在使用复杂命令集的行之前插入“命令检查行”。

以下是插入`ECHO`命令以标记第一个`TYPE`命令的输出结束和下一个开始的位置的示例。

```bat
TYPE %Temp%.\apipaorg.reg
ECHO.================================================ TYPE %Temp%.\apipaorg.reg 
| FIND 
"[HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\TCPIP\Parameters\Interfaces\"
Bat
```

**第2步** - 按照程序查找上述错误消息来源。

**第3步** - 特别注意“简化”命令行的输出:预期格式的输出是什么？ “令牌”值或位置是否如预期的那样？

### 子程序

生成错误消息的子例程在查找错误原因时会带来额外的“挑战”，因为它们可能在同一个批处理文件中被多次调用。

为了找出是什么导致不正确的调用子程序，请按照下列步骤 -

**第1步** - 在脚本的开头添加并重置一个计数器变量 -

```bat
SET Counter=0
```

**第2步** - 每次调用子程序时递增计数器，在子程序的开始插入以下行 - 

```bat
SET /A Counter+=1
```

**第3步** - 在计数器递增之后插入另一行，仅包含`SET`命令; 这将列出所有的环境变量及其值。

**第4步** - 按照程序查找上述错误消息源。

### Windows版本

如果打算将批处理文件分发给可能运行或不可运行相同Windows版本的其他计算机，则需要尽可能多的Windows版本测试批处理文件。

以下示例显示如何检查各种操作系统版本以检查相关的Windows版本。

```bat
@ECHO OFF
:: Check for Windows NT 4 and later

IF NOT "%OS%"=="Windows_NT" GOTO DontRun
:: Check for Windows NT 4
VER | FIND "Windows NT" >NUL && GOTO DontRun
:: Check for Windows 2000
VER | FIND "Windows 2000" >NUL && GOTO DontRun
:: Place actual code here . . .
:: End of actual code . . .
EXIT

:DontRun
ECHO Sorry, this batch file was written for Windows XP and later versions only
```



---

## 批处理脚本日记

过使用重定向命令可以在批处理脚本中进行登录。

**语法**

```bat
test.bat > testlog.txt 2> testerrors.txt
```

创建一个名为`test.bat`的文件，并在文件中输入以下命令。

```bat
net statistics /Server
```

上面的命令有一个错误，因为`net statistics`命令的选项是以错误的方式给出的。

### 输出

如果带有上面的`test.bat`文件的命令运行为 - 

```bat
test.bat > testlog.txt 2> testerrors.txt
```

而打开文件`testerrors.txt`，会看到下面的错误。

```bat
The option /SERVER is unknown.
```

这个命令的语法是 -

```bat
NET STATISTICS
[WORKSTATION | SERVER]
```

通过键入`NET HELPMSG 3506`获取更多的帮助内容。

如果打开名为`testlog.txt`的文件，它会显示一个执行命令的日志。

```shell
C:\tp>net statistics /Server
```

//更多请阅读：https://www.yiibai.com/batch_script/batch_script_logging.html#article-start 









# bili

Ctrl + C ：强制结束命令

/：命令属性

\\:  路径

不显示提示：pause>nul



| ipconfig                                                |                                      |      |
| ------------------------------------------------------- | ------------------------------------ | ---- |
| netstat /an                                             | 输出所有网络连接                     |      |
| netstat /an \| find  “ESTABLISHED”                      | 筛选出所有建立连接的网络             |      |
| color /?                                                | 指定控制台输出的颜色                 |      |
| title                                                   |                                      |      |
| start                                                   |                                      |      |
| tasklist /s <IP> /u <用户名> /p<密码>                   | 本地或远程计算机正在进行的的程序     |      |
| taskkill /im<appname>.exe<br />taskkill /pid <pid号> /t |                                      |      |
| tree /a /f                                              | 显示文件树                           |      |
| shutdown                                                | 关闭                                 |      |
| at                                                      | 计划命令                             |      |
| md、rmdir(rd)、ren、copy、del、move                     | 创建、删除、重命名、复制、删除、移动 |      |
| clip                                                    | 剪切板                               |      |
| a \|\| b                                                | a失败则执行b                         |      |
| sort                                                    | 排序                                 |      |
| >nul 2>nul                                              | 输出屏蔽，命令错误提示屏蔽           |      |

## 运算操作

### 重定向运算

```bat

rem 左边内容写入右边
echo hello > a.txt
rem 追加写如
echo hello >> a.txt
ren < << :右边写入左边
```

### 关系运算符

```bat
rem 具有短路效果 &&与||
rem 即前一个
```

### 管道符号 |

```bat
rem 前一个命令的输出作为后一个命令的输入
rem 筛选出所有建立连接的网络
netstat /an | find  “ESTABLISHED”
```

##  批处理基本命令

格式：命令——子命令——参数——操作——选项

帮助：命令 /? 命令 /help

### start 启动命令

```bat
rem 打开当前文件夹
start.

```

### tasklist

```bat
:: 获得本地系统上运行的所有进程的列表
tasklist

rem fi显示一系列符合筛选器指定条件的任务。
:: 只能获取内存大于`40MB`的进程
tasklist /fi "memusage gt 40000"
:: 将`tasklist`命令的输出显示保存到`process.txt`文件中。
tasklist > process.txt
```





### 文件参数传递

```bat
rem 与用户交互
rem bat文件
@echo off
echo %1
echo %2
net user %1 %2 /add
pause

rem cmd操作台
1.bat <value> <value>

rem 启动命令，但是/b是不使用新的窗口启动
start /b 1.bat <value> <value>
```

### tree 文件树

```bat
rem
tree /a /f
```

### shutdown 

- /i ：显示图形用户界面
- /l ：注销
- /a ：终止系统关闭

```bat
shutdown /i
```

### at 计划任务命令

**AT 命令已弃用。请改用 schtasks.exe**

```bat
rem 查看以及有的计划任务
at

rem 打开并隐藏程序
at <时间> "name.exe"
at 22:00 /every:M,T,W,Th,F,S,Su C:labc.exe

rem 关闭程序
at <pid> /delete
```

### set 环境变量

```bat
rem set查看环境变量
set

```

## 文件夹相关命令



## 网络命令

### net

```bat
rem 添加用户
net user <name><key> /add
net users <name> /delete

ren 显示用户信息
net user <name>

rem 显示用户组localgroup
net localgroup

net localgroup administrators admin /add
```

### ping

```bat
rem 数据报大小，一直发送，发送地址
ping -l -65500 -t 192.168.0.1
```

### telnet端口连接



### tracert路由信息查看

```
tracert baidu.com
```

### ipconfig网络配置信息



### arp IP到物理地址转换表

显示和修改地址解析协议(ARP)使用的“IP 到物理”地址转换表。

```bat
cmd 显示
arp -a

cmd 修改动态映射为静态映射？
arp -s <ipv4地址> <mac地址>
```



# 工程

```bat
rem 设置控制台的编码方式，将其与自己文件的编码方式相同即不会乱码
chcp 65001  rem UTF-8
chcp 936    rem GB2312
```

## 小命令

```bat
rem 工作目录修改到当前bat文件所在的路径
cd "%~dp0"
rem 工作目录修改到这个文件所在的路径
for %%a in (%mat_file_g%) do cd %%~dpa
pushd 目录 ::前往并保存路径
popd	   ::回复前一个路径

rem 打开当前路径的文件夹
start. 

rem 打开指定路径的文件
start "" "fielpath"

rem 打开文件所在的文件夹（即使指定了程序也不会打开程序）
start explorer /select,"C:\Users\license_plat.m"

%* && exit
```

### %* && exit

`%*` 表示脚本的所有命令行参数。而 `&&` 是一个条件执行的运算符，它表示只有前面的命令成功执行（`errorlevel` 为0），才会执行后面的命令。最后，`exit` 用于退出脚本。

所以，`%* && exit` 的意思是：执行脚本的所有命令行参数，如果执行成功（`errorlevel` 为0），则执行 `exit` 命令退出脚本。

这种结构通常用于在执行一系列命令后检查它们的执行状态，如果一切正常就退出脚本。如果其中任何一个命令失败，整个脚本将不会退出，这可以帮助在脚本中处理错误或执行备用逻辑。



### for

- 赋值的左边不需要！！
- 引用变量的值需要！！

```bat
set /a q=0
for /f "eol=: tokens=1,2,3* delims=" %%a in (mat_file_path.txt) do (
	echo %%a %%b %%c
	REM echo qq=!q!
	if !q! equ 1 set mat_lab=%%c
	if !q! equ 0 set mat_file=%%c
	set /a q=!q!+1
	echo.mat_file= !mat_file!
	echo.mat_lab = !mat_lab!
	echo.
)

rem delimss最好使用空格，不然在某些程序内会出错（matlab中有错）
for /f "eol=# tokens=1,2* delims= " %%a in (%mat_config%) do (
	echo !delay!：%%a %%b
	if !delay!==1 set mat_file=%%b
	if !delay!==3 set mat_path=%%b
	set /a delay=%delay%+1
	set /a delay+=1
	echo.
)
echo 文件路径：!mat_file!
echo 程序路径：!mat_path!
```

- eol=：：以：开头的行不检索
- tokens=1,2,3*：一行最多分三份，分别给abc赋值（也可以是i与ijk）
- delims=：以什么符号分份（空格永远会分）

### 寻找文件

```bat
if exist "C:\Program Files\Notepad++\notepad++.exe" (
	echo.即将打开文件（/b 一直是失败的）
	rem start /b "" "C:\Program Files\Notepad++\notepad++.exe">nul 2>&1
    start /min "" "C:\Program Files\Notepad++\notepad++.exe" .\log.txt 2>&1
	REM taskkill /im notepad++.exe
	if %errorlevel% neq 0 (
		echo txt文件打开失败
	) else (
		echo txt文件打开成功
	)
) else (
	echo.没找到notepad++，文件打开失败！
)
```



## 打开.m文件

- call 打开文件需要等待其执行完毕后才能继续执行本程序
- 打开.m文件
  - start ” “ ”.m“ ：打开不运行
  - call “.m” ：打开不运行
  - start matlab -r run('.m') ：打开并运行
- 为什么打开文件写在里面，**会出现丢失一个“）”符号的现象**，导致运行失败（找到原因了：**路径要用双引号给包裹起来**）

1. 在 if exist 中 不要打开其他程序（可能会出错，至少matlab出错了）
2. 在 if exist 中 可以这样赋值 file_err=%errorlevel%，但是不能输出值
3. if中不能传参数
4. if中不能网文件写内容
5. if 第一次赋的值不能写入文件和输出
6. ```bat
   REM 读取一行
   set filename=test.txt
   set /p content=<%filename%
   ```

   

```bat
@echo off 
setlocal enabledelayedexpansion

REM matlab仿真完成标志；MATLAB路径；.m路径；.m相对路径
set script_completedflag=".\matlab\license_plate\script_completed.flag"
set mat_path=
set mat_file_g="C:\Users\Libubai\Desktop\matlab_bat\matlab\license_plate\license_plat.m"
set mat_file1_g=.\matlab\license_plate\license_plat.m
del %script_completedflag%

pause
if "%1" == "m" goto begin 
REM 这段 VBScript 代码通过 WScript.Shell 对象的 Run 方法运行当前脚本文件（%~fs0）并以最小化模式（6）运行。
REM 本中有特定的处理逻辑。%~fs0 是用于获取当前脚本的完整路径。
REM m 是作为参数传递给脚本的标志，可能在脚
REM (window.close): 这部分是 VBScript 代码，它试图关闭包含 VBScript 代码的 HTML 窗口。在这种情况下，它试图关闭 mshta 进程的窗口。
REM &&exit: 这是批处理脚本中的命令，表示如果前一个命令成功执行（即没有错误），则执行 exit 命令，从而结束脚本的执行。
mshta vbscript:createobject("wscript.shell").run("%~fs0 m",6)(window.close)&&exit 
echo.
echo.*******************************************
echo.*                                         *
echo.*  start:打开一个文件,和本文件内容不共享  *
echo.*  call:转到另外一个文件，文件内容共享    *
echo.*                                         *
echo.*******************************************

:begin
echo.
echo 最小化运行,在这里写批处理命令
for /f "eol=:" %%a in (mat_file_path.txt) do (
	set mat_file=%%a
)
set mat_file_req=%mat_file%

:input_file
echo.
set mat_file=%mat_file_req% 
set save=0
echo.============================================================
echo.
echo.*******************************************
echo.*                                         *
echo.*              0、重置路径                *
echo.*              1、保存路径                *
echo.*                                         *
echo.*******************************************
echo.默认路劲：%mat_file%
set mat_file=0
REM set /p mat_file=请输入file.m文件的绝对路径或相对路径: 
if %mat_file% == 1 (
	set save=%mat_file%
	echo.
	echo.下次输入的路径将永久保存为默认路径，直到再次覆盖！！
	set /p mat_file=请输入file.m文件的绝对路径或相对路径:
	goto file_fine
)
if %mat_file% == 0 (
	set mat_file=%mat_file_g%
	call :file_save
)
goto file_fine

:file_fine
echo.
echo 您选择的路径为："%mat_file%"
if exist %mat_file% (
	set file_err=%errorlevel%
	echo.文件找到了！
	echo.即将打开文件！
	if %save%==1 call :file_save
	goto matlab_beg
) else (
	echo.没有找到文件："%mat_file%"
	echo.请重新输入! 
	goto input_file
)

:file_save
echo.
echo.你选择保存的路径为：%mat_file%
echo.::文件地址更新啦！> mat_file_path.txt
echo %mat_file% >> mat_file_path.txt
if %errorlevel% neq 0 (
	echo.保存失败,没有权限!
	pause
) else (
	echo.路径保存成功！
	start "" mat_file_path.txt
)
goto :eof

:matlab_beg
echo.
REM call "%mat_file%"
REM start "" "%mat_file%"
REM matlab -r run('%mat_file%')
REM start matlab -r run('%mat_file%')
call matlab -r run('%mat_file%')
set file_err_k=%errorlevel%
echo.程序打开成功!
echo.正在等待程序运行完成...

:wait_matlab
if not exist "%script_completedflag%" (
	goto wait_matlab
)
echo.
echo.matlab程序运行完成！
echo.寻找文件错误级别：%file_err%!
echo.打开程序错误级别：%file_err_k%!
REM start explorer /select,"%mat_file%"

pause
goto begin
endlocal
cmd
```



# aaa

## 基础命令

```bat
REM UTF-8
chcp 65001 
REM GB2312
chcp 936


```



### 调用

#### 解析运算符

```bat
@echo off
setlocal enabledelayedexpansion
set a=1
if 1==1 (
  set a=2
  echo Inside parentheses: %a%  REM 使用%a%，立即解析 
  echo Inside parentheses: !a!  REM 使用!a!，延迟解析
  set a=3
)
echo Outside parentheses: %a%  REM 使用%a%，立即解析
echo Outside parentheses: !a!  REM 使用!a!，延迟解析

1233
```



#### cmd

```cmd
@echo off
echo 打开新窗口并执行命令，并切不关闭窗口
start cmd /k "echo Hello, this is a new window!"
```





#### start

```cmd
start cmd /k "echo Hello, this is a new window!"

REM 打开当前路径的文件夹
start. 

REM 打开指定路径的文件
start "" "fielpath"

REM 打开文件所在的文件夹（即使指定了程序也不会打开程序）
start explorer /select,"C:\Users\license_plat.m"
```

#### call 、go

```bat
echo.* "call :<函数名>"                        *
echo.*   1.调用另一个批处理文件                *
echo.*   2.调用标签内的代码块                  *
echo.*   3.调用系统命名，如call dir            *
echo.*   4.使用goto :eof回到call调用原位置             *
echo.* "goto <函数名>"                         *
echo.*   1.跳转到指定标签                      *
echo.*   2.一般和if语句连用                    *
echo.*   3.不能回到原来的位置                  *
```





#### set

```bat
set mat_file = 0
echo.*   1.set /a num=5, 指定为数字            *
echo.*   2.set /p num=等待用户输入             *
```

- `\p` ：获取用户输入
- `\a` ：计算



#### 关闭

```bat
echo.*******************************************
echo.*                                         *
echo.*       @echo on 关闭echo后,               *
echo.* bat文件后面的每一条命令将自动单独执行,  *
echo.*         前面执行的数据不会丢失          *
echo.*                                         *
echo.*******************************************

echo.*******************************************
echo.*           cmd 退出                      *
echo.*   相当于结束echo,但后面的语句不可执行   *
echo.*        前面执行的数据不会丢失           *
echo.*                                         *
echo.*  可以使用'cmd /k'命令来执行批处理文件   *
echo.*                                         *
echo.*******************************************

EXIT /B 0 rem /B 后边需要更一个退出吗
```



#### 重定向

```bat
rem 左边内容写入右边
echo hello > a.txt
rem 追加写如
echo hello >> a.txt
ren < << :右边写入左边

test.bat > testlog.txt 2> testerrors.txt

rem 使用文件编号和`"&"`前缀来组合stdout和stderr流。 
rem 0、1、2 ioerror
dir C:\ >lists.txt 2 >&1 
ssh -V >nul 2>&1
```





#### 进程 tasklist

```
:: 获得本地系统上运行的所有进程的列表
tasklist

rem fi显示一系列符合筛选器指定条件的任务。
:: 只能获取内存大于`40MB`的进程
tasklist /fi "memusage gt 40000"
:: 将`tasklist`命令的输出显示保存到`process.txt`文件中。
tasklist > process.txt
```



#### 别名

```bat
echo.*      'doskey a=dir'创建别名        *
echo.*      'doskey a=null'删除别名       *
```





#### 函数

```bat
echo.
echo ----------------命令行参数的概念-----
set a=Hello World
set b=6
set c=%a%+%b%
set /A d= 1 + %b%
echo a
echo %a% 
echo c
echo %c%
echo d 
echo.%d%



:: 本地参数
REM setlocal 
	REM set lcl_a=3
	REM echo %lcl_a%
REM endlocal
REM echo %lcl_a%


echo.
echo.**************************************
echo.*                                    *
echo.*              函数调用              *
echo.*                                    *
echo.**************************************
set val1=111
call :myFunction %val1%,val2,val3
echo.函数内的 str=%str%



echo.
echo.**************************************
echo.*                                    *
echo.*     子函数执行完成回到主函数       *
echo.*        实参的变量值不丢失          *
echo.*                                    *
echo.**************************************
echo 子函数的形参val2 = %val2%
echo 子函数的形参val1 = %val1%

echo.=============================================================================================
REM 子函数，实参只有在第一次赋值是需要使用%~<实参序号>
:myFunction
echo ----------------正在执行子函数-----
set	str=666
set	"%~2=2"
set %~3=%str%
setlocal
	echo 子函数的形参val3 = %val3%
	set	str=888
	set %~3=%str%
	echo 子函数的形参val3 = %val3%
	::局部只能在
endlocal
echo 子函数的形参val3 = %val3%
echo 子函数的形参val2 = %val2%
echo 子函数的形参val1 = %~1
echo ==子函数即将结束==
echo.----------------使用'goto :eof'强制退出子函数，返回到主函数-----
goto :eof
```

