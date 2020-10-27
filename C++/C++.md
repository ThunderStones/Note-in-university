<center><h1>C++</h1></center> 

<center><h2>P1.编程基础</h2></center>

## 第二章 程序设计基础

---

### 2.3 从键盘中读取输入

- 使用 `cin` 从键盘读取输入 `cin >> x1`

- 读取多个输入。`cin >> x1 >> x2 >> x3`

	- 在输入时，可以输入三个用空格隔开的字符，按下**回车**，也可以每输入一个就按**回车**

### 2.4 标识符

​	标识符是程序中定义类似变量、函数之类元素的名字

​	标识符遵循的命名规则：

- 是一个字符序列，**可以**包含字母、数字和下划线，**不能**以数字开头
- 不能使用保留字
- 为保证可移植性，建议长度小于31个字符

### 2.5 变量

- 变量声明（variable declaration）

	* 语法 

		`datatype variableName`

	* 如果数据类型相同，则可以用以下方式命名

		`datatype variable1, variable2,..., variablen`

-   初始化变量

	-   ```c++
		int count = 1;
		//等价于
		int count;
		count = 1;
		```
	- ```c++
		int i(1), j(2);
		//等价于
		int i = 1, j = 2;#
		```

### 2.7 命名常量

​	`const datatype CONSTANTNAME = value`

- 习惯上，常量的名字用大写

### 2.8 数值数据类型及其运算

#### 2.8.1 数值类型



- | 类型名           | 同义表示             | 值域              | 空间占用 |
	| :--------------- | -------------------- | ----------------- | -------- |
	| `short`          | `short int`          | -2^15^ ~ 2^15^-1  | 16bit    |
	| `unsigned short` | `unsigned short int` | 0 ~ 2^16^-1       | 16bit    |
	| `int signed`     |                      | -2^31^ ~ 2^31^-1  | 32bit    |
	| `unsigned`       | `unsigned int`       | 0 ~ 2^32^-1       | 32bit    |
	| `long`           | `long int`           | -2^31^ ~ -2^31^-1 | 32bit    |
	| `unsigned long`  | `unsigned long int`  | 0 ~ 2^32^-1       | 32bit    |


```
double:     所占字节数：8    最大值：1.79769e+308    最小值：2.22507e-308
long double:     所占字节数：16    最大值：1.18973e+4932    最小值：3.3621e-4932
float:         所占字节数：4    最大值：3.40282e+38    最小值：1.17549e-38
```

- 在c++的头文件<limit>中，有`INT_MAX,INT_MIN,LONG_MIN,LONG_MAX,FLT_MIN,FLT_MAX,DBL_MIN,DBL_MAX`这些常量。

```c++
#include <iostream>
#include <limits>
using namespace std;

int main()
{
    cout << "INT_MIN is" << INT_MIN << endl;
    cout << "INT_MAX is" << INT_MAX << endl;
    cout << "LONG_MIN is" << LONG_MIN << endl;
    cout << "LONG_MAX is" << LONG_MAX << endl;
    cout << "FLT_MIN is" << FLT_MIN << endl;
    cout << "FLT_MAX is" << FLT_MAX << endl;
    cout << "DBL_MIN is" << DBL_MIN << endl;
    cout << "DBL_MAX is" << DBL_MAX << endl;
    
    return 0;
}
```

- `sizeof函数`

	可用`sizeof函数`查看变量在所使用的机器上所占用空间的大小，单位为字节（byte）。

#### 2.8.2 数值文字常量

- 文字常量（literal）就是在程序中直接出现的常量值。
- 不同进制表示
	1. 二进制前缀`0b`，如`0b1011010`
	2. 八进制前缀`0`，`016`
	3. 十六进制前缀`0x`，`0x1AF`

#### 2.8.3 数值运算符

- 当除法操作的两个操作数都是**整数**时，除法操作的结果是整数的商，小数部分会被截断，如 `5/2=2`
- 取模运算符（%）的运算对象只能是整数，运算结果的符号取决于被除数

### 2.13 数值类型转换

- 语法`static_cast<type>(value)`等价于`(type)value`
- 数值类型转换并不改变被转换变量的值

## 第三章

### 3.2 bool数值类型

- 1代表true，0代表false。控制台输出是，true会显示成1，false会显示成0
- 将数值赋给bool变量时，任何不是0的值都是true，0代表false

### 3.3 if语句

```c++
//单分支if语句
if (boolean-expression)
{
    statements;
}
//如果括号内为单一的语句，那么括号可以省略
if (boolean-expression)
    statements;
```

### 3.4&3.5 多分支if-else语句

```c++
//双分支if-else语句
if (boolean-expression)
{
    statement(s)-for-the-true-case;
}
else
{
    statement(s)-for-the-false-case;
}

//多分支if语句
if (boolean-expression)
{
    statement(s);
}
else if (boolean-expression)
{
    statement(s);
}
...
else
{
    statement(s);
}
```

### 3.9 生成随机数

- 使用`rand()`函数来获得随机**整数**，该函数包含于`cstdlib`头文件中
- 可使用`cstdlib`头文件中的`srand(seed)`函数来改变种子的值，为确保每一次种子的值都不一样，可以调用`time(0)`
- 生成区间[m,n]的整数  `rand() % (n - m + 1) + m;`
- 生成区间[a,a+b]的整数 `rand() % b + a`

### 3.10 逻辑运算符

| 运算符 | 名字 |
| :----: | :--: |
|  `!`   |  非  |
|  `&&`  |  与  |
|  `||`  |  或  |

### 3.13 switch语句

```c++
switch (switch-expression)
{
    case value1: statement(s);
    case value2: statement(s);
    case value3: statement(s);
    case value4: statement(s);
    default: statement(s);
}
```

- `switch-expression`必须产生一个整型值
- `value1(1.2,3,...)`是整型常量表达式，表达式里不能含有变量，不能是浮点型
- 执行完一个case语句后，若无break语句，下一个符合条件的case语句仍会被执行
- `default`语句是可选的，不符合任何case时执行
- `break`会终止switch语句

### 3.14 条件表达式

```c++
boolean-expression ? expression1 : expression2;
//如果布尔表达式为真，该条件表达式的值为expression1，否则为expression2
```

### 3.15运算符优先级和结合性

| 优先级 | 操作符                                                       |                             描述                             |  结合性  |
| ------ | ------------------------------------------------------------ | :----------------------------------------------------------: | :------: |
| 1      | () [] -> . :: ++ --                                          | 调节优先级的括号操作符 数组下标访问操作符 通过指向对象的指针访问成员的操作符 通过对象本身访问成员的操作符 作用域操作符 后置自增操作符 后置自减操作符 | 从左到右 |
| 2      | ! ~ ++ -- - + * & (type) [sizeof](http://www.cppreference.com/keywords/sizeof.html) | 逻辑取反操作符 按位取反(按位取补)  前置自增操作符 前置自减操作符 一元取负操作符 一元取正操作符 解引用操作符 取地址操作符 类型转换操作符 返回对象占用的字节数操作符 | 从右到左 |
| 3      | ->* .*                                                       | 在指针上通过指向成员的指针访问成员的操作符 在对象上通过指向成员的指针访问成员的操作符 | 从左到右 |
| 4      | * / %                                                        |              乘法操作符 除法操作符 取余数操作符              | 从左到右 |
| 5      | + -                                                          |                    加法操作符 减法操作符                     | 从左到右 |
| 6      | << >>                                                        |                按位左移操作符 按位右移操作符                 | 从左到右 |
| 7      | < <= > >=                                                    | 小于比较操作符 小于或等于比较操作符 大于比较操作符 大于或等于比较操作符 | 从左到右 |
| 8      | == !=                                                        |               等于比较操作符 不等于比较操作符                | 从左到右 |
| 9      | &                                                            |                         按位与操作符                         | 从左到右 |
| 10     | ^                                                            |                        按位异或操作符                        | 从左到右 |
| 11     | \|                                                           |                         按位或操作符                         | 从左到右 |
| 12     | &&                                                           |                         逻辑与操作符                         | 从左到右 |
| 13     | \|\|                                                         |                         逻辑或操作符                         | 从左到右 |
| 14     | ? :                                                          |                        三元条件操作符                        | 从右到左 |
| 15     | = += -= *= /= %= &= ^= \|= <<= >>=                           | 赋值操作符 复合赋值操作符(加法) 复合赋值操作符(减法) 复合赋值操作符(乘法) 复合赋值操作符(除法) 复合赋值操作符(取余) 复合赋值操作符(按位与) 复合赋值操作符(按位异或) 复合赋值操作符(按位或) 复合赋值操作符(按位左移) 复合赋值操作符(按位右移) | 从右到左 |
| 16     | ,                                                            |                          逗号操作符                          | 从左到右 |

## 第四章 数学函数、字符和字符串

### 4.2 数学函数

C++的`cmath`头文件中有很多有用的函数

#### 4.2.1 三角函数

```c++
sin()
cos()
tan()
asin()
acos()
atam()
```

#### 4.2.2 指数函数

- `exp(x)` 返回e^x^
- `pow(a,b)` 返回a^b^
- `log(x)` 返回ln x
- `sqrt(x)` 返回$\sqrt{x}$
- `log10(x)` 返回 lg x

#### 4.2.3 近似函数

- `ceil(x)` 向上取整，返回值类型为double
- `floor(x)` 向下取整，返回值类型为double

#### 4.2.4 min、max和abs函数

### 4.3 字符数据类型和操作符

#### 4.3.3 特殊字符的转义序列

| 转义字符 | 意义                                | ASCII码值（十进制） |
| -------- | ----------------------------------- | ------------------- |
| \a       | 响铃(BEL)                           | 007                 |
| \b       | 退格(BS) ，将当前位置移到前一列     | 008                 |
| \f       | 换页(FF)，将当前位置移到下页开头    | 012                 |
| \n       | 换行(LF) ，将当前位置移到下一行开头 | 010                 |
| \r       | 回车(CR) ，将当前位置移到本行开头   | 013                 |
| \t       | 水平制表(HT) （跳到下一个TAB位置）  | 009                 |
| \v       | 垂直制表(VT)                        | 011                 |
| \\       | 代表一个反斜线字符''\'              | 092                 |
| \'       | 代表一个单引号（撇号）字符          | 039                 |
| \"       | 代表一个双引号字符                  | 034                 |
| \?       | 代表一个问号                        | 063                 |
| \0       | 空字符(NULL)                        | 000                 |
| `\ddd`   | 1到3位八进制数所代表的任意字符      | 三位八进制          |
| `\xhh`   | 1到2位十六进制所代表的任意字符      | 二位十六进制        |

### 4.10 格式化控制台输出

| 流操纵算子            | 作  用                                                       |
| --------------------- | ------------------------------------------------------------ |
| `dec`                 | 以十进制形式输出整数                                         |
| `hex`                 | 以十六进制形式输出整数                                       |
| `oct`                 | 以八进制形式输出整数                                         |
| `fixed`               | 以普通小数形式输出浮点数                                     |
| `scientific`          | 以科学计数法形式输出浮点数                                   |
| `left`                | 左对齐，即在宽度不足时将填充字符添加到右边                   |
| `right`               | 右对齐，即在宽度不足时将填充字符添加到左边                   |
| `setbase(b)`          | 设置输出整数时的进制，b=8、10 或 16                          |
| `setw(w)`             | 指定输出宽度为 w 个字符，或输人字符串时读入 w 个字符         |
| `setfill(c)`          | 在指定输出宽度的情况下，输出的宽度不足时用字符 c 填充（默认情况是用空格填充） |
| `setprecision(n)`     | 设置输出浮点数的精度为 n。  在使用非 fixed 且非 scientific 方式输出的情况下，n 即为有效数字最多的位数，如果有效数字位数超过 n，则小数部分四舍五人，或自动变为科学计 数法输出并保留一共 n 位有效数字。  在使用 fixed 方式和 scientific 方式输出的情况下，n 是小数点后面应保留的位数。 |
| `setiosflags(flag)`   | 将某个输出格式标志置为 1                                     |
| `resetiosflags(flag)` | 将某个输出格式标志置为 0                                     |
| `boolapha`            | 把 true 和 false 输出为字符串                                |
| `noboolalpha`         | 把 true 和 false 输出为 0、1                                 |
| `showbase`            | 输出表示数值的进制的前缀                                     |
| `noshowbase`          | 不输出表示数值的进制.的前缀                                  |
| `showpoint`           | 总是输出小数点                                               |
| `noshowpoint`         | 只有当小数部分存在时才显示小数点                             |
| `showpos`             | 在非负数值中显示 +                                           |
| `noshowpos`           | 在非负数值中不显示 +                                         |
| `skipws`              | 输入时跳过空白字符                                           |
| `noskipws`            | 输入时不跳过空白字符                                         |
| `uppercase`           | 十六进制数中使用 A~E。若输出前缀，则前缀输出 0X，科学计数法中输出 E |
| `nouppercase`         | 十六进制数中使用 a~e。若输出前缀，则前缀输出 0x，科学计数法中输出 e。 |
| `internal`            | 数值的符号（正负号）在指定宽度内左对齐，数值右对 齐，中间由填充字符填充。 |

### 4.11 简单的文件输入输出

#### 4.11.1 写入文件

```c++
#include <fstream>  //定义了ofstream类
//声明ofstream类型的变量
ofstream output;
//调用open函数,创建文件，如果文件存在，则覆盖
output.open("number.txt")
//写入数据
output << 95 << " " << 56
//关闭文件
output.close()
```

#### 4.11.2 读取一个文件

```c++
#include <fstream>  //定义了ifstream类
//声明ifstream类型的变量
ifstream input;
//调用open函数,打开文件
input.open("number.txt")
//读取数据
input >> variable1
//关闭文件
input.close()
```



## 第五章 循环

### 5.2 `while`循环和`do-while`循环

```c++
//先判断条件，再执行循环体
while (loop-continuation-condition)
{
	statement(S);
}

//先执行循环体，再判断条件
do
{
    statement(s);
} while (loop-continuation-condition)
```

#### 5.2.6 输入和输出重定向

我不明白

#### 5.2.7读取所有输入

- `eof()`函数由于检测是否到达文件末尾，当没有可读的内容时，返回true

### 5.4 for循环

```c++
for (initial-action; loop-continuation-condition; action-after-each-iteration)
{
    statement(s);
}
```

### 5.7 最小化数字问题

```c++
#include <iostream>
using namespace std;

int main()
{
    double sum = 0;
    
    for (double i = 0.01; i <= 1.0; i += 0.01)
    {
        sum += i;
    }
    cout << sum;
    return 0;
}
```

- 最终输出为49.4而非50.5。原因为浮点数的保存为近似值，因此，应尽量避免使用浮点数来确定循环次数

- 可以这样更改for循环来避免错误

	```c++
	for (int count = 1; count < 100; count++)
	{
	    sum += currentValue;
	    currentValue += 0.01;
	}
	```

### 5.8 实例

#### 5.8.1 蒙特卡洛模拟

使用蒙特卡洛模拟来预估$\pi$的值

```c++
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main()
{
    const int NUMBER_OF_TRIAL = 1000000;
    int numberOfHit = 0;
    srand(time(0));
    
    for (int i = 0; i <= NUMBER_OF_TRIAL; i++)
    {
        double x = rand() * 2.0 / RAND_MAX -1;
        double y = rand() * 2.0 / RAND_MAX -1;
        if (x*x +y*y <= 1)
            numberOfHit++;
    }
    
    double pi = 4.0 * numberOfHit / NUMBER_OF_TRIAL;
    cout << pi
}
```

### 5.8.2 十进制转换为十六进制

```c++

```

