# **一、命名约定**
 

最重要的一致性规则是命名管理，命名风格直接可以直接确定命名实体是：类型、变量、函数、常量、宏等等，无需查找实体声明，我们大脑中的模式匹配引擎依赖于这些命名规则。

命名规则具有一定随意性，但相比按个人喜好命名，一致性更重要，所以不管你怎么想，规则总归是规则。

## **1. ****通用命名规则（****General Naming Rules****）**
采用下划线法，变量名中的每一个逻辑断点都有一个下划线来标记,字母一律采用小写。函数命名、变量命名、文件命名应具有描述性，不要过度缩写，类型和变量应该是名词，函数名可以用“命令性”动词。

例如：print_employee_paychecks()；

尽可能给出描述性名称，不要节约空间，让别人很快理解你的代码更重要，好的命名选择：

int num_errors;    // Good.

int num_completed_connections;  // Good.

丑陋的命名使用模糊的缩写或随意的字符：

int n;                                                              // Bad - meaningless.

int nerr;                                                         // Bad - ambiguous abbreviation.

int n_comp_conns;                                     // Bad - ambiguous abbreviation.

类型和变量名一般为名词：如 FileOpener、num_errors。

函数名通常是指令性的，如 OpenFile()、set_num_errors()，访问函数需要描述的更细致，要与其访问的变量相吻合。

**缩写**：

除非放到项目外也非常明了，否则不要使用缩写，例如： 

int num_dns_connections;  // Most people know what "DNS" stands for.

int price_count_reader;      // OK, price count. Makes sense.

int wgc_connections;  // Only your group knows what this stands for.

int pc_reader;                  // Lots of things can be abbreviated "pc".

## **2. ****文件命名（****File Names****）**
文件名要全部小写，用下划线（_）分割。

可接受的文件命名：

my_useful_class.cpp

 通常，尽量让文件名更加明确，http_server_logs.h 就比 logs.h 要好，定义类时文件名一般成对出现，如 foo_bar.hpp 和 foo_bar.cpp，对应类 FooBar。

## **3. ****类型命名（****Type Names****）**
采用下划线法，类型名中的每一个逻辑断点都有一个下划线来标记,字母一律采用小写，例如：

class url_table { ...}.

## **4. ****变量命名（****Variable Names****）**
变量名一律小写，单词间以下划线相连，类的成员变量以下划线结尾，如my_exciting_local_variable、my_exciting_member_variable_。

   

对全局变量没有特别要求，少用就好，可以以 g_或其他易与局部变量区分的标志为前缀。

  

## **5. ****函数命名（****Function Names****）**
采用下划线法，函数名中的每一个逻辑断点都有一个下划线来标记,字母一律采用小写。

## 6**. ****命名空间（****Namespace Names****）**
命名空间的名称是全小写的，如：namespace stub，如有必要其命名基于下划线法：namspace account_history。

  

## **7. ****枚举命名（****Enumerator Names****）**
  

枚举值应采用下滑线法，单词间以下划线相连：nh_asset_list_type。

注：目前主链代码中95%以上的枚举命名采用上述方法，但还剩下几个枚举命名方法不一致，为了统一，规范采用下滑线法。

## **8. ****宏命名（****Macro Names****）** 
通常是不使用宏的，如果绝对要用，全部大写 、使用下划线：

#define PI_ROUNDED 3.0

 

#define  MY_EXCITING_ENUM_VALUE 9

# **二、注释**
  

注释虽然写起来很痛苦，但对保证代码可读性至为重要，下面的规则描述了应该注释什么。

注释语言一律采用英文。

## **1. ****注释风格（****Comment Style****）**
  

 单行采用//，连续多行采用/**/。

## **2. ****文件注释（****File Comments****）**
 在每一个文件开头加入版权公告，然后是文件内容描述。

 

**法律公告和作者信息**：

 

每一文件包含以下项，依次是：

1)   版权（copyright statement）：如 Copyright 2008 Google Inc.；

2）许可版本（license boilerplate）：为项目选择合适的许可证版本，如 [Apache 2.0](http://en.wikipedia.org/wiki/Apache_2.0_licensing)、[BSD](http://en.wikipedia.org/wiki/BSD_license)、[LGPL](http://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License)、[GPL](http://en.wikipedia.org/wiki/GNU_General_Public_License)；

 3)   作者（author line）：标识文件的原始作者。

  如果你对其他人创建的文件做了重大修改，将你的信息添加到作者信息里，这样当其他人对该文件有疑问时可以知道该联系谁。

## **3. ****类注释（****Class Comments****）**  
   每个类的定义要附着描述类的功能和用法的注释。

  

注意：

	**1.****   ****关于注释风格，很多**** C++****的**** coders ****更喜欢行注释，****C coders ****或许对块注释依然情有独钟，或者在文件头大段大段的注释时使用块注释；**

**   2.****   ****文件注释可以炫耀你的成就，也是为了捅了篓子别人可以找你；**

	**3.****   ****注释要言简意赅，不要拖沓冗余，复杂的东西简单化和简单的东西复杂化都是要被鄙视的；**

	4**.****  ****TODO ****很不错，有时候，注释确实是为了标记一些未完成的或完成的不尽如人意的地方 ，这样一搜索，就知道还有哪些活要干。**

# **三、格式**
  

代码风格和格式确实比较随意，但一个项目中所有人遵循同一风格是非常容易的，整个项目服从统一的编程风格是很重要的，这样做才能让所有人在阅读和理解代码时更加容易。

    

## **1. ****行长度（****Line Length****）**
 每一行代码字符数不超过 80。

  

## **2. ****非**** ****ASCII**** ****字符（****Non-ASCII Characters****）**
  

尽量不使用非 ASCII 字符，使用时必须使用 [UTF-8](http://en.wikipedia.org/wiki/UTF-8)[ ](http://en.wikipedia.org/wiki/UTF-8)格式。

   

哪怕是英文，也不应将用户界面的文本硬编码到源代码中，因此非 ASCII 字符要少用。特殊情况下可以适当包含此类字符，如，代码分析外部数据文件时，可以适当硬编码数据文件中作为分隔符的非 ASCII 字符串；更常用的是（不需要本地化的）单元测试代码可能包含非 ASCII 字符串。此类情况下，应使用 UTF-8 格式，因为很多工具都可以理解和处理其编码，十六进制编码也可以。

  

## **3. ****空格还是制表位（****Spaces vs. Tabs****）**
  

 只使用空格，每次缩进 2 个空格。

 使用空格进行缩进，不要在代码中使用 tabs，设定编辑器将 tab 转为空格。

  

## **4. ****函数声明与定义（****Function Declarations and Definitions****）**
  

通常情况下，返回类型和函数名在同一行，合适的话，参数也放在同一行。

  

如果同一行文本较多，容不下所有参数：

  

return_type ClassName::ReallyLongFunctionName(Type par_name1,  

Type par_name2,

Type par_name3) {

DoSomething();

}

  

 甚至连第一个参数都放不下：

 注意以下几点：

1)   返回值总是和函数名在同一行；

2)   左圆括号（open parenthesis）总是和函数名在同一行；

3)   函数名和左圆括号间没有空格；

4)   圆括号与参数间没有空格；

5)   左大括号（open curly brace）总在最后一个参数同一行的末尾处；

6)   右大括号（close curly brace）总是单独位于函数最后一行；

7)   右圆括号（close parenthesis）和左大括号间总是有一个空格；

8)   函数声明和实现处的所有形参名称必须保持一致；

9)   所有形参应尽可能对齐；

10)   缺省缩进为 2 个空格；

11)   独立封装的参数保持 4 个空格的缩进。

## **5. ****条件语句（****Conditionals****）**
  

提倡关键字 else 另起一行。

## **6. ****循环和开关选择语句（****Loops and Switch Statements****）**
  

switch 语句可以使用大括号分块；空循环体应使用{}或 continue。

  

如果有不满足 case 枚举条件的值，要总是包含一个 default（如果有输入值没有 case 去处理，编译器将报警）。

## **7. ****指针和引用表达式（****Pointers and Reference Expressions****）**
  

句点（.）或箭头（->）前后不要有空格，指针/地址操作符（*、&）后不要有空格。

## **8. ****布尔表达式**
如果一个布尔表达式超过标准行宽（80 字符），如果断行要统一一下。

## **9. ****函数返回值（****Return Values****）**
  

return 表达式中不要使用圆括号。 

函数返回时不要使用圆括号：

return x;  // not return(x);

  

 

