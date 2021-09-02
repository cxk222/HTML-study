---
title: 01-js语法基础
date: 2021-07-19
tags: javascript
categories: javascript
---
# js语法基础

#### 一、发展历史
1.javascript是1995年网景公司雇佣布兰登(Brendan Eich)开发的全新语言。
2.javascript最初是为了实现浏览器客户端交互
3.ECMAScript与javascript关系
``前者是后者的规格，后者是前者的一种实现``

#### 二、书写位置
  行内式 内嵌式 外链式
  <!--more-->
#### 三、变量
1.语法 ``var 变量名 = 值``
2.注意：
>   1）一个变量名只能存储一个值
    2）再次赋值时会覆盖前一次的值
    3）变量名称区分大小写

3.命名规范----语义化、驼峰命名
>   + 一个变量名称可以有数字、字母、英文、下划线、美元符号$组成；
>   + 区分大小写；
>   + 不能由数字开头，不能使用中文；
>   + 不能是保留字或关键字；
>   + 不能出现空格；

#### 四、数据类型
1. 基本数据类型
    1）数值类型（number）————NaN非数值，也是数值类型
    2）字符串类型（String）————被引号包括的所有内容
    3）布尔类型（boolean）————true/false
    4）未定义的（undefined）
    5）空类型（null）

    ```javascript
        // 数值类型
        var a = 100
        console.log('a=',a,'a的类型=',typeof(a))
        // 字符串类型
        var b = '内容'
        console.log('b=',b,'b的类型=',typeof(b))
        // 布尔类型
        var c = true
        var d = false
        console.log('c/d=',c,d,'c/d的数据类型=',typeof(c),typeof(d))
        // 未定义的类型
        var e = undefined
        console.log('e=',e,'e的数据类型=',typeof(e))
        // 空类型
        var f = null
        console.log('f=',f,'f的数据类型',typeof(f))
    ```
2. 复杂数据类型————对象类型 object/函数类型 function等
3. 判断数据类型 typeof
4. 数据类型转换
    1）其他数据类型 ==> number
    + Number(变量)
    空字符串转换为0 &emsp; 非数字字符串/undefined——>NaN &emsp; true为0，flase为0 &emsp; null——>0
    ```javascript
        //数据类型转换
        var g = 200
        var i = ''
        var h = Number(g)
        var j = Number(i)
        console.log(h,typeof(h),j,typeof(j))
    ```
     - parseInt(变量)
       - 从第一位开始检查，是数字就转换，知道一个不是数字的内容
       - 开头就不是数字，那么直接返回NaN
       - 不认识小数点，只能保留整数
  
    ```js
        // 小数取整
        var m = 100.5
        var n = parseInt(m)
        var s = parseFloat(m)
        console.log(n,typeof(n))
        console.log(s,typeof(s))
    ```
    - parseFloat
       + 从第一位开始检查，是数字就转换，知道一个不是数字的内容
       + 开头就不是数字，那么直接返回NaN
       + 认识一次小数点
    
    - 隐式转换（除加法以外的运算）
      + 运算符两边都是可运算数字才行
      + 如果运算符任何一遍不是一个可运算数字，那么就会返回NaN
      + 加法不可以用

    ```js
        // 隐式转换
        var x = 200
        var y = 10
        var z = x-y
        console.log(z)
    ```
    2)其他类型转换成字符串
     + 变量.toString()
        有一些数据类型不能使用tostring()方法，比如undefined和null
     +  String(变量)
        所有数据类型都可以
     + 使用加法运算
        + 在JS里面，＋由两个含义
        + 字符串拼接:只要＋任意一边是字符串，就会进行字符串拼接
        + 加法运算:只有+两边都是数字的时候，才会进行数学运算
  
    3）其他数据变成布尔
    #### 五、运算符
    1. 数学运算符
    1）+ 
    &emsp;只有两边都是数字才会进行加法运算 
    &emsp;两边只要有任意一边是字符串就会进行字符串拼接
    2）-
    &emsp; 会自动执行减法运算
    &emsp; 会自动把两边都转换为数字进行运算
    3）*
    &emsp; 会自动执行乘法运算
    &emsp; 会自动把两边都转换为数字进行运算
    4）/
    &emsp; 会自动执行除法运算
    &emsp; 会自动把两边都转换为数字进行运算
    5）%
    &emsp; 会自动执行余数运算
    &emsp; 会自动把两边都转换为数字进行运算
    2. 赋值运算符
    `=`
    &emsp; 把 = 右边的赋值给 = 左边的变量名
    `+=` `-=` `*=` `/=` `%=`
    3. 比较运算符
     `>=` `<=` `>` `<`
    4. 逻辑运算符
     `&&且` `||或` `!非`
    3. 自增自减运算符
     `++在前` 先加1 再运算 再赋值
     `++在后` 先运算 再赋值 再加1
    4. 条件运算符
     `三目运算符`