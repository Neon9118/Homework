# 第五章：MATLAB

本部分主要详细介绍了MATLAB各种操作

---

- [第一部分：MATLAB程序设计](#第一部分matlab程序设计)
  - [一、基本界面](#一基本界面)
  - [二、基本操作](#二基本操作)
  - [三、数据输入输出](#三数据输入输出)
  - [四、程序设计](#四程序设计)
  - [五、函数文件](#五函数文件)
  - [六、全局变量和局部变量](#六全局变量和局部变量)
- [第二部分：文件操作](#第二部分文件操作)
  - [一、 基本命令](#一-基本命令)
  - [二、文件的打开与关闭](#二文件的打开与关闭)
  - [三、文件的读写操作](#三文件的读写操作)
  - [四、数据文件定位写操作](#四数据文件定位写操作)
- [第三部分：绘图功能](#第三部分绘图功能)
  - [一、二维图形](#一二维图形)
  - [二、特殊坐标图形](#二特殊坐标图形)
  - [三、其它图形函数](#三其它图形函数)
  - [四、三维图形](#四三维图形)
- [第四部分：实战](#第四部分实战)
  - [实战一：股票数据分析+可视化](#实战一股票数据分析可视化)
  - [实战二：机器学习——鸢尾花分类](#实战二机器学习鸢尾花分类)
- [第五部分：总结、](#第五部分总结)


# 第一部分：MATLAB程序设计

---

## 一、基本界面

| 区域 | 作用 |
|------|------|
| 命令行窗口 | 输入命令，看结果 |
| 工作区 | 查看所有变量 |
| 当前文件夹 | 浏览文件，切换目录 |
| 编辑器 | 写脚本（.m文件） |

**一句话**：命令窗口干活，编辑器写脚本，工作区盯数据。

---

## 二、基本操作

- ### 变量

```matlab
a = 5;              % 分号不显示结果
b = 10;             % 不加分号就打印
name = 'Neon';
```

- ### 矩阵操作

```matlab
A = [1 2 3; 4 5 6; 7 8 9];    % 3×3矩阵
A(2,3)          % 第2行第3列 → 6
A(2,:)          % 第2行全部
A(:,1)          % 第1列全部
B = A'          % 转置
C = A * B       % 矩阵乘法
D = A .* A      % 逐元素乘（点运算）
```

**【例1】  求解线性方程组AX=B**                   

  A=$\begin{bmatrix} 1 & 1.5 & 2 & 9 & 7 \\ 0 & 3.6 & 0.5 & -4 & 4\\ 7 & 10 & -3 & 22 & 33 \\ 3 & 7 & 8.5 &21 & 6 \\ 3 & 8 & 0 & 90 & -20\end{bmatrix}$,B=$\begin{bmatrix}  3 \\  -4 \\ 20 \\ 5 \\ 16 \end{bmatrix}$,X=?


![](https://i.ibb.co/gbH2P1Lg/mt1.png)

**【例2】  求方程 $x^4 + 7x^3 +9x-20=0$的全部根**

![](https://i.ibb.co/7dc28d5m/mt2.png)



## 三、数据输入输出

- ### input函数
  用于向计算机输入一个参数。
  调用格式：  `A=input(提示信息，选项)；`
  >注：‘s’选项，则允许用户输入一个字符串。例如想输入一个人的姓名，可采用命令`xm=input('What''s your name:','s')`
  
**【例1】  求一元二次方程$a^2 +bx+c=0$的根。**
  
![](https://i.ibb.co/SDbFs0vH/mt3.png)

- ### pause函数
  暂停程序的执行。
  调用格式： `pause(延迟秒数)`
  >注：如果省略延迟时间，直接使用pause，则将暂停程序，直到用户按任一键后程序继续执行。
  

-  ### disp函数
  命令窗口输出函数。
  调用格式： `disp(输出项)`
  >注：输出项为字符串或矩阵。
  
**【例2】**
```matlab
        A='Hello,MATLAB';
        disp(A)
```

![](https://i.ibb.co/tMjhrzvJ/mt4.png)

## 四、程序设计

### 1、选择结构
  选择结构的语句有if语句和switch语句。 


- #### if语句

```matlab
%格式一： 
 if  条件
 语句组
 end

%格式二： 
 if  条件
     语句组1
 else
    语句组2
end

%格式三：  
if  条件1
    语句组1
elseif  条件2
    语句组2
    ……
elseif  条件m
    语句组m
else
    语句组m+1
end

```
**【例1】输入三角形的三条边，求面积。** 

![](https://i.ibb.co/gMTKYHWd/mt5.png)


**【例2】  输入一个字符，若为大写字母，则输出其后继字符，若为小写字母，则输出其前导字符，若为其他字符则原样输出。**

![](https://i.ibb.co/MkkKL3sH/mt6.png)


- #### switch语句
  switch语句根据变量或表达式的取值不同，分别执行不同的语句。



```matlab

         case  值1
            语句组1
         case  值2
            语句组2
               ……
         case  值m
            语句组m
         otherwise
            语句组m+1
         end


```

**【例3】  根据变量 num 的值来决定显示的内容。**

![](https://i.ibb.co/1H3fRYq/mt7.png)


### 2、循环结构

实现循环结构的语句：for语句和while语句。

- #### for语句
```matlab
%格式：   
for 循环变量=表达式1:表达式2:表达式3
    循环体语句
end

```
>注：其中表达式1的值为循环变量的初值，表达式2的值为步长，表达式3的值为循环变量的终值。步长为1时，表达式2可以省略。


- #### While语句

```matlab
%格式为：
         while (条件)
             循环体语句
         end
```

- #### 循环的嵌套
  多重循环的嵌套层数可以是任意的。可以按照嵌套层数，分别叫做二重循环、三重循环等。处于内部的循环叫作内循环，处于外部的循环叫作外循环。

**【例4】  求[100,1000]以内的全部素数。**

![](https://i.ibb.co/Kcc8NQ1b/mt8.png)

---
## 五、函数文件
函数文件是另一种形式的M文件，每一个函数文件都定义一个函数。

### 1、函数文件格式
函数文件由function语句引导，

```matlab
%其格式为：
   function 输出形参表=函数名(输入形参表)
          注释说明部分
          函数体
```

>注：其中函数名的命名规则与变量名相同。输入形参为函数的输入参数，输出形参为函数的输出参数。当输出形参多于1个时，则应该用方括号括起来。

**【例5】  编写函数文件求小于任意自然数n的Fibonacci数列各项。**

![](https://i.ibb.co/nsgFMKLQ/mt9.png)

### 2．函数调用
函数文件编制好后，就可调用函数进行计算了。
如上面定义ffib函数后，调用它求小于2000的Fibonacci数。

```matlab
%函数调用的一般格式是：
        [输出实参表]=函数名(输入实参表)
```
**【例6】  利用函数的递归调用，求n！。**

![](https://i.ibb.co/TxghmCpc/mt10.png)


### 3 ．函数所传递参数的可调性
MATLAB在函数调用上有一个与众不同之处：函数所传递参数数目的可调性。凭借这一点，一个函数可完成多种功能。
>在调用函数时，MATLAB用两个永久变量nargin和nargout分别记录调用该函数时的输入实参和输出实参的个数。只要在函数文件中包含这两个变量，就可以准确地知道该函数文件被调用时的输入输出参数个数，从而决定函数如何进行处理。

**【例7】  nargin用法示例**

![](https://i.ibb.co/vvwtsK8W/mt11.png)


## 六、全局变量和局部变量
在MATLAB中，全局变量用命令`global`定义。函数文件的内部变量是局部的，与其他函数文件及MATLAB工作空间相互隔离。全局变量的作用域是整个MATLAB工作空间，即全程有效。所有的函数都可以对它进行存取和修改。因此，定义全局变量是函数间传递信息的一种手段。

**【例8】  全局变量应用示例**

![](https://i.ibb.co/7NrW4D9G/mt12.png)

---
# 第二部分：文件操作
Matlab环境下的文件与其它系统一样，也有二类文件组成，一是文件，又称M文件，另一类是数据文件。系统除提供了文件的一般管理功能外，还提供了对数据文件进行操作的特殊功能函数。

## 一、 基本命令

### 1.help  帮助命令
  ` help 命令名`

![](https://i.ibb.co/yB44WjZF/mt13.png)



### 2. what  显示目录内容命令
 `what [目录名]`

![](https://i.ibb.co/Zpx15TWC/MT14.png)


### 3．type 显示文件内容命令
`type 文件名`

![](https://i.ibb.co/pGscypR/mt15.png)

### 4.寻找命令
`lookfor  命令或字符串`

![](https://i.ibb.co/x850xFx1/mt16.png)

### 5．which 寻找函数命令
`which  函数名`

![](https://i.ibb.co/SwGCpt8f/mt17.png)


### 6 ．path 路径控制命令
`path [路径]` 显示或改变搜索路径。

例如： `path （path，‘d：\test\aaa’)`


### 7．who,whos 显示变量命令
显示当前变量。 whos命令更详细。

### 8 ．load,save  取出与保存结果命令
从磁盘上读出或保存计算结果。

例如： save test  %将变量存入test.mat文件中。
例如： save test x y  %仅保存x ，y 变量。

### 9 ．clear  清除变量命令
 `clear [变量名]`

例如： clear x y

### 10 ．disp  显示文本或变量内容命令
例如：      x=[1 2 3]
            disp(x)
            y=‘aaaaaaa’
            disp(y)

### 11 ．cd  改变目录命令
与DOS类似。

### 12 ．dir  显示目录内容命令
显示目录里的文件。
例如：dir \matlab\notebook

### 13．delete 删除文件或对象命令
`delete 文件名`   %不能用通配符

例如：H=PLOT（X，X）
     delete (H)


### 14．！ 执行系统命令
在Windows下运行。“！”用于执行DOS命令。
例如：！dir *.exe
显示当前目录里的EXE文件。

---
## 二、文件的打开与关闭

### 1. fopen打开文件


在读写文件之前，必须先用fopen命令打开一个文件，并指定允许对该文件进行的操作。文件操作结束后，应及时关闭文件，以免数据的丢失或误修改。

    `Fid= fopen(filename，permission)`

>其中filename为文件名，permission为文件格式，可以是下列格式之一：

permission|含义
:---:|:---:
‘r’|打开文件，读数据，文件必须存在。
‘w’|打开文件，写数据，若文件不存在，系统会自动建立。
‘a’|打开文件，在文件末尾添加数据。
‘r+’|打开文件，可以读和写数据，文件必须存在。
‘w+’|打开文件，供读与写数据用。
‘a+’|打开文件，供读与添加数据用。
‘W’|打开文件供写数据用，无自动刷新功能。
‘A’|打开文件供添加数据用，无自动刷新功能。


### 2  fclose关闭文件
文件在进行完读、写等操作后，应及时关闭，以保证文件的安全可靠。
`Sta=fclose(Fid)`   
关闭Fid所表示的文件。Sta表示关闭文件操作的返回代码，若关闭成功，返回0，否则返回–1。

 
## 三、文件的读写操作

### 1.二进制数据文件

- #### fread 读二进制数据文件。

`[A,COUNT]=fread(Fid,size,precision)`
>其中A为数据矩阵，COUNT返回所读取的数据元素个数。size为可选项，若不选用则读取整个文件内容，若选用它的值可以是下列值：

size|含义
:---:|:---:
N|读取 N个元素到一个列向量。
inf|读取整个文件。
[M,N]|读数据到M×N的矩阵中，数据按列存放。

>precision用于控制所读数据的精度格式。缺省格式为uchar，即无符号字符格式。

- #### fwrite 写二进制数据文件。

`COUNT=fwrite (Fid, A, precision)`

**例1**

![](https://i.ibb.co/YFrbwz3x/mt18.png)

### 2.文本文件

- #### fscanf  读ASCII文本文件
`[A,COUNT]= fscanf (Fid, format, size)`
>其中A为数据矩阵，用以存放读取的数据，COUNT返回所读取的数据元素个数。format用以控制读取的数据格式，由%加上格式符组成，格式符为：d, i, o, u, x, e, f, g, s, c与[. . .]  

- #### fprintf  写ASCII数据文件
`COUNT= fprintf(Fid, format, A,…)`
>其中A为要写入文件的数据矩阵，先按format格式化数据矩阵A，后写入到Fid所指定的文件。

![](https://i.ibb.co/PZPvXHMJ/mt19.png)



## 四、数据文件定位写操作

### 1.fseek函数定位文件位置指针
`status=fseek（Fid, offset, origin)`
>其中Fid为文件句柄，offset表示位置指针相对移动的字节数，若为正整数表示向文件尾方向移动，若为负整数表示向文件头方向移动，origin表示位置指针移动的参照位置，它的取值有三种可能：’cof ’表示文件的当前位置，’bof ’表示文件的开始位置，’eof ’表示文件的结束位置。若定位成功status返回值为0，否则返回值为–1。

### 2. ftell函数返回文件指针的当前位置。
`position=ftell (Fid)`
>返回值为从文件开始到指针当前位置的字节数。若返回值为–1表示获取文件当前位置失败。

**【例2】下述程序段说明了函数fseek和ftell的使用。**

![alt text](https://i.ibb.co/8DjsfBMg/mt20.png)

---
# 第三部分：绘图功能
作为一个功能强大的工具软件，Matlab具有很强的图形处理功能，提供了大量的二维、三维图形函数。

## 一、二维图形

### 1.plot函数

- 函数格式：`plot(x,y)`  其中x和y为坐标向量
- 函数功能：以向量x、y为轴，绘制曲线。

**【例1】同时绘制正、余弦两条曲线$Y_1=SIN（X）$和$Y_2=COS（X）$**

![](https://i.ibb.co/spT6ct2L/mt21.png)


- #### 线型与颜色:`plot(x,y1,’cs’,...)`
>其中c表示颜色， s表示线型。

**【例2】 用不同线型和颜色重新绘制例1图形**

![](https://i.ibb.co/b5BhgLkT/AA1.png)

>其中参数'go'和'b-.'表示图形的颜色和线型。g表示绿色，o表示图形线型为圆圈；b表示蓝色，-.表示图形线型为点划线。

- #### 图形标记
`title(‘加图形标题');`      
`xlabel('加X轴标记');`     
`ylabel('加Y轴标记');`    
`text(X,Y,'添加文本');`
 
>在绘制图形的同时，可以对图形加上一些说明，如图形名称、图形某一部分的含义、坐标说明等，将这些操作称为添加图形标记。

- #### 设定坐标轴
>用户若对坐标系统不满意，可利用axis命令对其重新设定。

`axis([xmin xmax ymin ymax]) `设定最大和最小值
`axis （’auto’）` 将坐标系统返回到自动缺省状态
`axis （’square’）`   将当前图形设置为方形
`axis （’equal’）`    两个坐标因子设成相等
`axis （’off’）`      关闭坐标系统
`axis （’on’）`       显示坐标系统


**【例3】 在坐标范围$0≤X≤2π$,$-2≤Y≤2$内重新绘制正弦曲线**

![](https://i.ibb.co/sp5TCSB1/AA2.png)



- #### 加图例
>把图例放置在图形空白处，用户还可以通过鼠标移动图例，将其放到希望的位置。
`legend('图例说明','图例说明');`  

![](https://i.ibb.co/nsc83YLf/AA3.png)


### 2.subplot函数


- #### subplot（m,n,p） 
该命令将当前图形窗口分成m×n个绘图区，即每行n个，共m行，区号按行优先编号，且选定第p个区为当前活动区。


**【例4】 在一个图形窗口中同时绘制正弦、余弦、正切、余切曲线**

![](https://i.ibb.co/Rkvv8mVZ/AA4.png)


- #### 多图形窗口
需要建立多个图形窗口，绘制并保持每一个窗口的图形，可以使用`figure`命令。
>每执行一次figure命令，就创建一个新的图形窗口，该窗口自动为活动窗口，若需要还可以返回该窗口的识别号码，称该号码为句柄。句柄显示在图形窗口的标题栏中，即图形窗口标题。用户可通过句柄激活或关闭某图形窗口，而`axis`、`xlabel`、`title`等许多命令也只对活动窗口有效。

![](https://i.ibb.co/vxqLdG2J/AA5.png)


- #### hold命令
若在已存在图形窗口中用plot命令继续添加新的图形内容，可使用图形保持命令hold。发出命令hold on后，再执行plot命令，在保持原有图形或曲线的基础上，添加新绘制的图形。

![](https://i.ibb.co/Rps0ktv3/AA6.png)

### 3.函数f(x)曲线
fplot函数则可自适应地对函数进行采样，能更好地反应函数的变化规律。
`fplot(fname，lims，tol)`
>其中fname为函数名，以字符串形式出现，lims为变量取值范围，tol为相对允许误差，其其系统默认值为2e-3。

**【例5】 为绘制$f(x)=cos(tan(πx))$曲线，可先建立函数文件fct.m**

![](https://i.ibb.co/NdHVqSwY/AA7.png)

---

## 二、特殊坐标图形

### 1.对数坐标图形

- #### loglog(x,y) 双对数坐标

**【例6】 绘制y=|1000sin(4x)|+1的双对数坐标图。**

![](https://i.ibb.co/39rqjKw2/AA8.png)

- #### 单对数坐标

**【例7】分别以X轴，y轴为对数重新绘制例6曲线**

![](https://i.ibb.co/nskMc2Nm/aa9.png)

### 2.极坐标图

函数`polarplot(theta,rho)`用来绘制极坐标图
>theta为极坐标角度，rho为极坐标半径

**【例8】 绘制$sin(2θ)cos(2θ)$（即四叶玫瑰线）的极坐标图**

![](https://i.ibb.co/VYbTtQc5/AA10.png)

---

## 三、其它图形函数

### 1.阶梯图形
函数`stairs(x,y)`可以绘制阶梯图形

![](https://i.ibb.co/9m7TMq4F/AA11.png)

### 2.条形图形
函数`bar(x,y)`可以绘制条形图形

![](https://i.ibb.co/MyK0d9kb/AA12.png)


### 3.填充图形
`fill(x,y,’c’)`函数用来绘制并填充二维多边图形，x和y为二维多边形顶点坐标向量。字符 ’c’ 规定填充颜色，其取值前已叙述。

![](https://i.ibb.co/G4S15DGF/AA13.png)

---

## 四、三维图形

### 1.plot3函数(最基本)
是将二维函数plot的有关功能扩展到三维空间，用来绘制三维图形。
`plot3(x1,y1,z1,c1,x2,y2,z2,c2,…) `
>其中x1,y1,z1…表示三维坐标向量，c1，c2…表示线形或颜色。
>函数功能：以向量x，y，z为坐标，绘制三维曲线。

**【例1】 绘制三维螺旋曲线**

![](https://i.ibb.co/WvMgGD3F/AA14.png)


### 2.mesh函数
mesh函数用于绘制三维网格图。在不需要绘制特别精细的三维曲面结构图时，可以通过绘制三维网格图来表示三维曲面。
>三维曲面的网格图最突出的优点是：它较好地解决了实验数据在三维空间的可视化问题。
`mesh(x,y,z,c)`
>其中x，y控制X和Y轴坐标，矩阵z是由(x，y)求得Z轴坐标，(x,y,z)组成了三维空间的网格点；c用于控制网格点颜色。


**【例2】 绘制三维网格曲面图**

![](https://i.ibb.co/JRw4yH8v/AA15.png)


### 3.surf函数
surf用于绘制三维曲面图，各线条之间的补面用颜色填充。surf函数和mesh函数的调用格式一致。
` surf (x,y,z)`
>其中x，y控制X和Y轴坐标，矩阵z是由x，y求得的曲面上Z轴坐标。

**【例3】 绘制三维曲面图形**

![](https://i.ibb.co/KjKC8Ptt/AA16.png)

### 4.视点
视点位置可由方位角和仰角表示。方位角又称旋转角为视点位置在XY平面上的投影与X轴形成的角度，正值表示逆时针，负值表示顺时针。仰角又称视角为XY平面的上仰或下俯角，正值表示视点在XY平面上方，负值表示视点在XY平面下方。
从不同视点绘制三维图形的函数为view。
 >`view(az,el)`中的az为方位角，el为仰角。通过系统提供的多峰函数peaks的绘制例子，可进一步说明视点对图形的影响，以及view(az,el)函数的使用。


**【例4】 不同视角图形**

![](https://i.ibb.co/qLyVvFy4/AA17.png)

### 5.等高线图
等高线图可通过函数`contour3`绘制。

**【例5】 多峰函数peaks的等高线图**

![](https://i.ibb.co/8nZn7zBV/AA18.png)

### 6.动画设计
`moviein`函数
>函数m=moviein(n)用来建立一个足够大的n列的矩阵m，用来保存n幅画面的数据，以备播放。

`movie`函数
>movie(m,n)以每秒n幅图形的速度播放由矩阵m的列向量所组成的画面。

**【例6】播放一个直径不断变化的球体**

![](https://i.ibb.co/Xkb5wqHZ/AA19.png)

![](https://i.ibb.co/4w2JpQxm/AA20.png)

---
# 第四部分：实战


## 实战一：股票数据分析+可视化

```matlab
% 模拟20天股票数据
dates = datetime('2026-07-01') + caldays(0:19);
price = [100, 102, 101, 105, 108, 107, 110, 112, 115, 113, ...
         116, 118, 120, 119, 122, 125, 123, 127, 130, 128]';

% 做成表格
stock = table(dates', price, 'VariableNames', {'Date', 'Close'});

% 计算指标
returns = diff(price) ./ price(1:end-1);           % 日收益率
ma5 = movmean(price, 5);                           % 5日均线
ma10 = movmean(price, 10);                         % 10日均线

% 可视化
subplot(2,2,[1 2]);
plot(stock.Date, stock.Close, 'b-o', 'LineWidth', 1);
hold on;
plot(stock.Date, ma5, 'r-', 'LineWidth', 1.5);
plot(stock.Date, ma10, 'g-', 'LineWidth', 1.5);
xlabel('日期'); ylabel('收盘价');
title('股票价格 & 移动均线');
legend('收盘价', '5日均线', '10日均线');
grid on;

subplot(2,2,3);
bar(stock.Date(2:end), returns * 100);
xlabel('日期'); ylabel('收益率(%)');
title('每日收益率');
grid on;

subplot(2,2,4);
histogram(returns * 100, 8);
xlabel('收益率(%)'); ylabel('频次');
title('收益率分布');
grid on;

% 统计摘要
fprintf('均价: %.2f\n', mean(price));
fprintf('波动率: %.2f%%\n', std(returns) * 100);
fprintf('最高: %.2f  最低: %.2f\n', max(price), min(price));
```

![](https://i.ibb.co/BVvJ3qfD/AA21.png)

---

## 实战二：机器学习——鸢尾花分类

```matlab
% 加载经典数据集
load fisheriris;

% 数据探索
fprintf('样本数: %d, 特征数: %d\n', size(meas));
fprintf('类别: %s\n', strjoin(unique(species), ', ')); 

% 划分训练集(70%)和测试集(30%)
rng(42);
n = size(meas, 1);
idx = randperm(n);
train_idx = idx(1:round(0.7*n));
test_idx = idx(round(0.7*n)+1:end);
X_train = meas(train_idx, :);
y_train = species(train_idx);
X_test = meas(test_idx, :);
y_test = species(test_idx);

% 训练 KNN 分类器
k = 5;
mdl = fitcknn(X_train, y_train, 'NumNeighbors', k);

% 预测 & 评估
y_pred = predict(mdl, X_test);
acc = sum(strcmp(y_pred, y_test)) / length(y_test) * 100;
fprintf('KNN (k=%d) 准确率: %.1f%%\n', k, acc);

% 混淆矩阵
figure;
cm = confusionchart(y_test, y_pred);
title(['KNN 分类结果 (准确率=' num2str(acc, '%.1f') '%)']);

% 可视化分类边界（取前两个特征）
figure;
gscatter(meas(:,1), meas(:,2), species, 'rgb', 'osd');
xlabel('花萼长度'); ylabel('花萼宽度');
title('鸢尾花分布（前两维特征）');
legend('Location', 'best'); grid on;
```

![](https://i.ibb.co/GQ4bsCc7/AA22.png)

---

# 第五部分：总结、

本次matlab学习是基于本科课程《数学建模》，对于MATLAB还有更复杂的用法，但主要是将MATLAB用于画图，就没有再往下更深入学习。