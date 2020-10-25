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
- 生成区间[m,n]的整数  `rand()%(n - m + 1) + m;`

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

![image-20201025182103898](C:\Users\Thunder Stone\Documents\GitHub\Note-in-university\C++\assert\C++\image-20201025182103898.png)

