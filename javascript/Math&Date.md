---
title: 数学对象Math和日期对象Date
date: 2021-07-29
tags: javascript
categories: javascript
decription: 
---

## Math数学对象
#### Math对象的方法
- acos(x)返回数的反余弦值
- asin(x)返回数的反正弦值
- atan(x)以介于-π/2与π/2弧度之间的数值来返回x的反正切值
- atan2(y,x)  返回从x轴到点（x,y）的角度（介于-π/2与π/2弧度之间）
- cos(x) 返回数的余弦
- exp(x) 返回e的指数
- log(x) 返回数的自然对数(底为e)
- pow(x,y)  返回x的y次幂
- sin(x) 返回数的正弦
- sqrt(x)返回数的平方根
- tan(x) 返回角的正切
- toSource()  返回该对象的源代码
- valueOf() 返回Math对象的原始值

<!--more-->

- **random()  返回0~1之间的随机数**
      - Math.random()这个方法是用来生成一个0~1之间的随机数
      - 每次执行生成的数字都不一样，但是一定是0~1之间的
      - 生成的数字包含0，但不包含1
    ```js
    <!-- 生成m,n之间的随机数 -->
    const getRandom = (m, n) => {
    let n1 = Math.max(m, n)
    let m1 = Math.min(m, n)
    return Math.floor(Math.random() * (n1 - m1)) + m1
    }
    ```
- **round(x)  把数四舍五入为最接近的整数**
- **floor(x)  对数进行下舍入**
- **ceil(x)对数进行上舍入**
 
```txt
Math.round()，Math.ceil()，Math.floor()的区别
 
1. Math.round()：根据“round”的字面意思“附近、周围”，可以猜测该函数是求一个附近的整数，看下面几个例子就明白。
 
    小数点后第一位<5
    正数：Math.round(11.46)=11
    负数：Math.round(-11.46)=-11
    
    小数点后第一位>5
    正数：Math.round(11.68)=12
    负数：Math.round(-11.68)=-12
    
    小数点后第一位=5
    正数：Math.round(11.5)=12
    负数：Math.round(-11.5)=-11
    
总结：（小数点后第一位）大于五全部加，等于五正数加，小于五全不加。
 
2. Math.ceil()：根据“ceil”的字面意思“天花板”去理解；
 
例如：
    Math.ceil(11.46)=Math.ceil(11.68)=Math.ceil(11.5)=12
    
    Math.ceil(-11.46)=Math.ceil(-11.68)=Math.ceil(-11.5)=-11
 
 
3. Math.floor()：根据“floor”的字面意思“地板”去理解；
 
例如：
    Math.floor(11.46)=Math.floor(11.68)=Math.floor(11.5)=11
    
    Math.floor(-11.46)=Math.floor(-11.68)=Math.floor(-11.5)=-12
```
- **abs(x) 返回数的绝对值**
```js
let num = -10
console.log(math.abs(num))//10
```
- **max(x,y)  返回x和y中的最大值**
- **min(x,y)  返回x和y中的最小值**
```js
console.log(Math.max(1,2,3,4,5))//5
```
- **toString()方法可以在数字转成字符串的时候给出一个进制数**
    - 语法：toString(你要转换的进制)
    ```js
    let num = 100
    console.log(num.toString(2)) //1100100
    console.log(num.toString(8)) //144
    console.log(num.toString(16)) //64
    ```
- **parseInt()方法可以在字符串转成数字的时候把字符串当成多少进制转成十进制**
    - 语法：parseInt(要转换的字符串，当成几进制来转换)
    ```js
    let str = 100
    console.log(parseInt(str,8)) // 64    把100当作一个八进制的数字转换成十进制后得到的结果
    console.log(parseInt(str,2)) // 4     把100当作一个二进制的数字转换成十进制后得到的结果
    console.log(parseInt(str,16)) // 256  把100当作一个十六进制的数字转换成十进制后得到的结果
    ```

## Date日期对象

#### new Date()
- new Date()在不传递参数的情况下是默认返回当前时间
  ```js
  let time = new Date()
  console.log(time) //当前时间 Sat Jul 29 2021 09:59:24 GMT+0800(中国标准时间)
  ```
- new Date()在传入参数的时候，可以获取到一个你传递进去的时间
  ```js
  let time = new Date('2021-07-29 09:56:52')
  console.log(time) // Sat Jul 29 2021 09：56：52 GMT+0800(中国标准时间)
  ```
#### new Date()的多种情况
1. 传递两个数字，第一个表示年，第二个表示月份
   ```js
    let time = new Date(2021,00)//月份从0开始计数，0表示1月，11表示12月
    console.log(time) //Fri Jan 01 2021 00:00:00 GMT+0800 (中国标准时间)
   ```
2. 传递三个数字，前两个不变，第三个表示该月份的第几天，从1到31
   ```js
   let time = new Date(2021,00,07)
   console.log(time) //Thu Jan 07 2021 00:00:00 GMT+0800 (中国标准时间)
   ```
3. 传递四个数字，前三个不变，第四个表示当天的几点，从0到23
   ```js
   let time = new Date(2021,07,07,10)
   console.log(time) // Sat Aug 07 2021 10:00:00 GMT+0800 (中国标准时间)
   ```
4. 传递五个数字，前四个不变，第五个表示的是该小时的多少分钟，从0到59
   ```js
    let time = new Date(2021,07,07,10,13)
    console.log(time) //Sat Aug 07 2021 10:13:00 GMT+0800 (中国标准时间)
   ```
5. 传递六个数字，前五个不变，第六个表示该分钟的多少秒，从0到59
   ```js
    let time = new Date(2021,07,07,10,13,56)
    console.log(time) //Sat Aug 07 2021 10:13:56 GMT+0800 (中国标准时间)
   ```
6. 传入字符串的形式
   ```js
    console.log(new Date('2021'))
    //Fri Jan 01 2021 08:00:00 GMT+0800 (中国标准时间)
    console.log(new Date('2021-08'))  
    //Sun Aug 01 2021 08:00:00 GMT+0800 (中国标准时间)
    console.log(new Date('2021-08-07'))
    //Sat Aug 07 2021 08:00:00 GMT+0800 (中国标准时间)
    console.log(new Date( '2021-08-07 10:'))  
    //Sat Aug 07 2021 10:00:00 GMT+0800 (中国标准时间) 
    console.log(new Date( '2021-08-07 10:19:'))   
    //Sat Aug 07 2021 10:19:00 GMT+0800 (中国标准时间)
    console.log(new Date( '2021-08-07 10:19:13'))
    //Sat Aug 07 2021 10:19:13 GMT+0800 (中国标准时间)

#### 将日期字符串格式化成指定内容
- getFullYear()方法是得到指定字符串中的哪一年
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getFullYear()) //2019
    ```
- getMonth()方法是得到指定字符串中的哪一月
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getMonth()) //8
    ```
- getDate()方法是得到指定字符串中的哪一天
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getDate()) //7
    ```
- getHours()方法是得到指定字符串中的哪小时
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getHours()) //10
    ```
- getMinutes()方法是得到指定字符串中的哪分钟
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getMinutes()) //15
    ```
- getSeconds()方法是得到指定字符串中的哪秒钟
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getSeconds()) //25
    ```  
- getDay()方法是得到指定字符串中当前日期是一周中的第几天（周日是0，周六是6）
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getDay()) //6
    ``` 
- getTime()方法是得到执行时间到格林威治时间的毫秒数
    ```js
    let time = new Date(2021,08,07,10,15,25)
    console.log(time.getTime()) //1630980925000
    ```   
