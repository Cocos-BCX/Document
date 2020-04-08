# 1.问题描述
**在合约中进行正整数相乘计算的时候出现负值或计算结果错误，如下图：**

![图片](https://uploader.shimo.im/f/SOY7uATo7KcIS0YC.png!thumbnail)

# 2.问题追踪
**通过打印中间值变量，比较是否超出了数值范围；并****测试lua中的最大整数**

## **2.1****打印中间值变量追踪问题**
![图片](https://uploader.shimo.im/f/Ct3hhJfJd3k0jCAl.png!thumbnail)

## **2.2中间计算值大于lua虚拟机****_I64_MAX或LLONG_MAX**
```
// maximum signed 64 bit value
#define _I64_MAX      9223372036854775807i64
#define LLONG_MAX     9223372036854775807i64       // maximum signed long long int value
```
## **2.3lua虚拟机_I64_MAX和LLONG_MAX最大整数测试**
![图片](https://uploader.shimo.im/f/5KHIwzvvp4I3ppAc.png!thumbnail)

# 3.解决方案
**解决方案有两种：**

* 在合约中将大数值计算转化为浮点类型计算
* 增加合约最大整数i_max的API
## **3.1合约中将大数值转换为浮点类型计算**
![图片](https://uploader.shimo.im/f/MTpY70jcoFAASwgR.png!thumbnail)

* **当声明的变量大于整数最大值时，直接转为浮点类型；当间接计算超过最大整数值时会出现负数**

![图片](https://uploader.shimo.im/f/DyDeMY7U54wfpt0f.png!thumbnail)

## 3.2增加合约最大整数i_max的API
增加chainhelper:i_max，将计算与i_max比较，防止溢出等现象。

# 4.chainhelper:number_max和最大整数间误解
## 4.1打印chainhelper:number_max
* **链合约number_max声明的不是最大整数值，如下：**

![图片](https://uploader.shimo.im/f/ZISiCrzrFpYMbcoZ.png!thumbnail)

**从上图测试可以看出chainhelper:number_max是对应的浮点数。**

## 4.2增加chainhelper:i_max解决误解
增加最大整数值chainhelper:i_max，并更新对应的文档。

