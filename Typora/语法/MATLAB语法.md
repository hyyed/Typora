# MATLAB语法

0为黑、白为1

## 0、基础

### 数据类型numeric

在MATLAB中,数值类型的变量被默认为 double 类型的,可以使用类型转换将其转换为其他数值类型  

```matlab
class（变量）//显示变量的数据类型numeric
```

| 数值类型 | 描述           |
| -------- | -------------- |
| double   | 双精度浮点数   |
| single   | 单精度浮点数   |
| int8     | 8位带符号整数  |
| int16    | 16位带符号整数 |
| int32    | 32位带符号整数 |
| int64    | 64位带符号整数 |
| uint8    | 8位无符号整数  |
| uint16   | 16位无符号整数 |
| uint32   | 32位无符号整数 |
| uint64   | 64位无符号整数 |

### 字符串类型char

字符串在内存中是以**字符矩阵的形式存储**的,可以对其进行矩阵的索引以及赋值操作  

```matlab
s1 = 'h';
uint16(s1) % 得到 104

str1 = 'hello';
str2 = 'world';
str3 = [str1 str2];
size(str3) % 得到 [1 10]
str4 = [str1; str2];
size(str4) % 得到 [2 5]  
```

```matlab
str = 'aardvark';
'a' == str % 得到 [1 1 0 0 0 1 0 0]
str(str == 'a') = 'Z' % 得到 'ZZrdvZrk'
```

### 矩阵

矩阵检索时竖着来的，不是恒着；

### 关键字

```matlab
sob_threshole=0.05:0.01:0.14;
for i = 1:10
    sob_gray = edge(I_gray,'sobel',sob_threshole(i));
    subplot(2,5,i);
    imshow(sob_gray);
    title_str = sprintf('sob_threshole:%g',sob_threshole(i));
    title(title_str);
end
```

```matlab
for i = 1:a*b
    sob_gray = edge(I_gray,'sobel',i);
    subplot(a,b,i);
    imshow(sob_gray);
    title_str = sprintf('sob_threshole:%g',i);
    title(title_str);
end
```

```matlab
for i = 1:a*b
    sob_gray = edge(I_gray,'sobel',i);
    switch (i)
        case 1
            subplot(a,b,i);
        case 2
            subplot(a,b,i);
        case 3
    end
    imshow(sob_gray);
    title_str = sprintf('sob_threshole:%g',i);
    title(title_str);
end
```

```matlab
%注意：for 的循环变量，尽量使用整型，否则 switch 的 i 的 case 不能完全匹配(就算把它乘10变为整数也不能完全匹配)
for i = 0.1:0.1:10
	sob_gray = edge(I_gray,'sobel',i);
    switch (i*10)
        case 1
            subplot(a,b,i);
        case 2
            subplot(a,b,i);
    end
    imshow(sob_gray);
    title_str = sprintf('sob_threshole:%g',i);
    title(title_str);
end
```









## 1、转义字符

反斜杠后的 `n` 表示一个特殊的转义字符，即换行符。它的作用是在字符串中创建一个换行的效果，将后续内容移到新的一行显示。

除了 `\n` 表示换行符外，还有其他常用的转义字符，它们都以反斜杠开始，后面跟一个特定的字符来表示不同的含义。以下是一些常见的转义字符及其含义：

- `\n`: 换行符，用于在字符串中创建一个新的一行。
- `\t`: 制表符，用于在字符串中插入一个水平制表符（Tab）。
- `\\`: 反斜杠，用于在字符串中插入一个反斜杠。
- `\'`: 单引号，用于在字符串中插入一个单引号。
- `\"`: 双引号，用于在字符串中插入一个双引号。



`%s` 是格式化输出中的一个特殊标记，用于指定输出字符串的位置。
这个标记在 `fprintf` 和 `sprintf` 等函数中使用，它允许在输出时将字符串插入到指定的位置。

除了 `%s` 表示字符串，还有一些其他常用的格式标记，它们用于指定输出不同类型的数据。以下是一些常见的格式标记及其含义：

- `%d` 或 `%i`: 表示输出一个有符号十进制整数。
- `%f` 或 `%e` 或 `%E`: 表示输出一个浮点数。
  - `%f` 用于输出定点数（小数点后有固定位数），
  - `%e` 或 `%E` 用于输出科学计数法表示的浮点数。
- `%u`: 表示输出一个无符号十进制整数。
- `%c`: 表示输出一个字符。
- `%g`: 表示输出一个浮点数或一个有符号整数，根据实际值选择最短的表示形式。
- `%x` 或 `%X`: 表示输出一个十六进制整数。`%x` 用小写字母表示十六进制数，`%X` 用大写字母表示。

```matlab
str = 'Hello';
num = 42;
pi_value = pi;

fprintf('String: %s\n', str);
fprintf('Decimal: %d\n', num);
fprintf('Floating-point: %f\n', pi_value);
fprintf('Character: %c\n', 'A');
fprintf('Scientific notation: %e\n', 1.23e6);
fprintf('Hexadecimal: %X\n', 255);
```

```yaml
String: Hello
Decimal: 42
Floating-point: 3.141593
Character: A
Scientific notation: 1.230000e+06
Hexadecimal: FF
```

## 2、文件操作

### 语法

在MATLAB中，'w+' 和 'wt' 都是文件打开模式（file open mode）的参数，用于在打开文件时指定文件的读写方式。它们之间的区别在于：

1. 'w+' (读写模式)：
   - 'w+' 模式是可读写模式（read-write mode），可用于读取文件内容和写入新内容。
   - 如果文件不存在，将创建一个新文件。
   - 如果文件已存在，会清空文件内容，然后可以进行读写操作。
   - 如果文件打开失败，则返回空文件标识符（file identifier）。
2. 'wt' (文本写入模式)：
   - 'wt' 模式是用于文本文件的写入模式（text write mode）。
   - 与 'w+' 相似，如果文件不存在，将创建一个新文件。
   - 但与 'w+' 不同的是，'wt' 模式打开文件后，会强制将行尾（End-of-Line，EOL）字符写入为默认的操作系统行尾符号（例如在Windows上是"\r\n"，在Linux上是"\n"），而不是 MATLAB 默认的行尾符号（"\n"）。这样做是为了确保文件在其他文本编辑器中也能正确显示换行符。

可以换成的其他模式包括：

1. 'r' (只读模式)：
   - 'r' 模式是只读模式（read mode），用于读取文件内容。
   - 如果文件不存在，打开操作将失败。
2. 'a' (追加模式)：
   - 'a' 模式是追加模式（append mode），用于在文件末尾添加内容。
   - 如果文件不存在，将创建一个新文件。
3. 'at' (追加文本写入模式)：
   - 'at' 模式是用于文本文件的追加模式。
   - 与 'a' 相似，如果文件不存在，将创建一个新文件。
   - 与 'wt' 不同的是，'at' 模式打开文件后，会强制将行尾字符写入为默认的操作系统行尾符号。
4. 'b' (二进制模式)：
   - 'b' 模式是用于二进制文件的模式。
   - 例如，'wb' 是二进制写入模式，'rb' 是二进制读取模式。

在选择文件打开模式时，请根据你的需求选择最合适的模式。如果要同时读取和写入文件，可以使用 'w+' 模式，如果要写入文本文件并确保行尾符号正确，可以使用 'wt' 或 'at' 模式。而如果只需读取文件内容，选择 'r' 模式即可。



### 例子

#### 1

```matlab
clc;
close all;
fild = fopen('gen_data.coe','wt');
fprintf(fild,'%s\n','memory_initialization_radix = 10');
fprintf(fild,'%s\n','memory_initialization_vector = ');
for j = 0:255
    if(j==255)
        fprintf(fild,'%g;',j);
    end
    if(j<255)
        fprintf(fild,'%g,\n',j);
    end
end

fclose(fild);
```

```yaml
memory_initialization_radix = 10
memory_initialization_vector = 
0,
1,
2,
3,
·····，
255;
```

#### 2

```matlab
fid=fopen('fifo_data.txt','w+');
for i =1:50
    for j = 1:50
        fprintf(fid,'%02x ',j-1);
    end
end
fclose(fid);
```

```
01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13 14
```

#### 3.chatGTP

```matlab
% 生成 0 到 255 的十进制数
decimal_data = 0:255;

% 将十进制数保存到 fifo_data.txt 文件中
file_path = 'E:/sources/fifo_sum/matlab/fifo_data.txt';
file_handle = fopen(file_path, 'wt');

if file_handle == -1
    error('无法打开文件或文件路径不正确');
end

fprintf(file_handle, 'memory_initialization_radix = 10;\n');
fprintf(file_handle, 'memory_initialization_vector =\n');

for i = 1:length(decimal_data)
    if i == length(decimal_data)
        fprintf(file_handle, '%d;', decimal_data(i));
    else
        fprintf(file_handle, '%d,\n', decimal_data(i));
    end
end

fclose(file_handle);
disp('fifo_data.txt 文件已生成。');
```

## 3、MATLAB输出tb仿真文件

在这个示例中，我们将使用Verilog进行简单的仿真，然后将仿真结果导出到一个文本文件中。接下来，我们使用MATLAB读取该文本文件并将仿真结果输出为图片。

### 1.Verilog

首先，我们需要编写一个简单的Verilog模块，例如一个4位计数器，每个时钟周期增加1。我们将在仿真中输出计数器的值到一个文本文件。

```verilog
verilogCopy codemodule counter(
    input wire clk,
    input wire rst,
    output reg [3:0] count
);

always @(posedge clk or posedge rst) begin
    if (rst) begin
        count <= 4'b0000;
    end else begin
        count <= count + 1;
    end
end

endmodule
```

### 2.Testbench

```verilog
module tb_counter;

reg clk;
reg rst;
wire [3:0] count;

counter dut (
    .clk(clk),
    .rst(rst),
    .count(count)
);

initial begin
    clk = 0;
    forever #5 clk = ~clk; // 周期为10个时间单位
end

initial begin
    rst = 1;
    #15; // 等待一段时间
    rst = 0; // 复位信号拉低
    #100; // 继续仿真一段时间
    $finish; // 结束仿真
end

endmodule
```

将上述Verilog代码和Testbench代码保存在文件中（如`counter.v`和`tb_counter.v`），然后使用你喜欢的仿真工具（如ModelSim）进行仿真。仿真工具会生成一个波形文件（如`wave.vcd`）。

### 3.MATLAB

在MATLAB中，我们将读取仿真输出的波形文件，并将仿真结果输出为一个图片。

```matlab
% 读取仿真输出的波形文件
filename = 'wave.vcd';
data = vcdread(filename);

% 获取计数器的信号数据
time = data.time;
count_values = data.signals.tb_counter__count;

% 绘制波形图
figure;
plot(time, count_values, 'b', 'LineWidth', 2);
xlabel('Time (ns)');
ylabel('Counter Value');
title('Counter Simulation Waveform');
grid on;

% 保存波形图为图片
output_image_file = 'counter_waveform.png';
saveas(gcf, output_image_file);

disp('波形图已保存为：');
disp(output_image_file);
```

运行上述MATLAB代码后，你会在MATLAB工作目录中找到一个名为`counter_waveform.png`的图片文件，其中包含计数器的仿真波形图。

请注意，这个示例只是一个简单的演示用例。在实际应用中，你可能需要根据具体的仿真输出文件格式和数据处理需求进行适当的调整。

### 4.Python

安装Python并安装Matplotlib库（如果尚未安装）。然后使用以下Python脚本来绘制波形图并将其保存为图片。

```python
import matplotlib.pyplot as plt
import vcd  # 需要安装 vcd库，用于解析VCD文件

# 读取VCD文件
vcd_file = "wave.vcd"
with open(vcd_file, "r") as f:
    vcd_data = f.read()

# 解析VCD数据
vcd_parser = vcd.VCDParser(vcd_data)
vcd_signals = vcd_parser.parse()

# 获取计数器信号数据
signal_name = "tb_counter/count"
count_signal = vcd_signals[signal_name]

# 提取时间和计数器值
time = []
count_values = []
for timestamp, value in count_signal:
    time.append(timestamp)
    count_values.append(value)

# 绘制波形图
plt.plot(time, count_values, label="Counter Value")
plt.xlabel("Time (ns)")
plt.ylabel("Counter Value")
plt.title("Counter Simulation Waveform")
plt.legend()

# 保存波形图为图片
output_image_file = "counter_waveform.png"
plt.savefig(output_image_file)
plt.show()

print("波形图已保存为：", output_image_file)
```

### 5.MTLB图片预处理

```matlab
clc;                            %清理命令行窗口
close all;                      %清理工作区
image = imread('logo.png');     %使用imread函数读取图片数据

figure;
imshow(image);                  %窗口显示图片
R = image(:,:,1);               %提取图片中的红色层生成灰度图像

figure;
imshow(R);                      %窗口显示灰色图像
[ROW,COL] = size(R);            %灰色图像大小参数
data = zeros(1,ROW*COL);        %定义一个初值为0的数组,存储转换后的图片数据
for r = 1:ROW
    for c = 1 : COL
        data((r-1)*COL+c) = bitshift(R(r,c),-5);    %红色层数据右移5位
    end
end

fid = fopen('logo.txt','w+');                       %打开或新建一个txt文件
for i = 1:ROW*COL
    fprintf(fid,'%02x ',data(i));                   %写入图片数据
end
fclose(fid);
```





















## 4、图片处理

```matlab
X = imread('真彩色转灰度.png');

%彩色转灰度
I = rgb2gray(X);
set(0,'defaultFIgurePosition',[100,100,1000,500]);
figure,
subplot(121);imshow(X);
subplot(122);imshow(I);
saveas(gcf,'gray_and.png');
saveas(gcf,'gray_and.tif');%为什么保存的信息为空
imwrite(I,'gray.png');

%直方图均衡
figure
I2 = histeq(I);
subplot(141);imhist(I);
subplot(142);imshow(I);
subplot(143);imhist(I2);
subplot(144);imshow(I2);
saveas(gcf,"histed.png");

%二值化
level = graythresh(I);bw = im2bw(I,level);
figure
subplot(121);imshow(I);
subplot(122);imshow(bw);

imtool(bw);
imageinfo("gray.png");

A=size(I);

%%目标计数
I_rice = imread("rice.png");
subplot(231);imshow(I_rice);
BG = imopen(I_rice,strel("disk",15));%开运算去除目标，只显示背景
subplot(232);imshow(BG);
I2_rice = imsubtract(I_rice,BG);
subplot(233);imshow(I2_rice);

%背景是否去除对二值化的影响
level_rice = graythresh(I2_rice);
bw_rice = im2bw(I2_rice,level_rice);
subplot(235);imshow(bw_rice);title("去除背景")
level1_rice = graythresh(I_rice);
bw1_rice = im2bw(I_rice,level1_rice);
subplot(234);imshow(bw1_rice);title("没去除背景")
saveas(gca,"rice_open_bw.png")
% level1 = imbinarize(I2_rice,"adaptive");
% subplot(234);imshow(level1);title("imbinarize")


%目标计数
[labled,numObject] = bwlabel(bw_rice,8);

RGB_labed = label2rgb(labled);%标记结果的彩色转换
subplot(236);imshow(RGB_labed);title("标记图像彩色显示")

% 交互选择
ObjI = bwselect(bw_rice);
imshow(ObjI);

figure('name','BG')
subplot(121);imshow(level_rice);
subplot(122);imshow(level1_rice);

[XX,map] = imread("gray_and.png");
RGB = ind2rgb(XX,map);
figure,imshow(XX,map);

```





