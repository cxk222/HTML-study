---
title: 表单和css基础
date: 2021-06-23
tags: html,css
categories: html,css
---
## 表单和css基础
#### 表单
###### 概念：在页面中负责数据采集功能的。

**1. 表单标签**

```html
<form  action='设置数据提交的地址' method='数据提交的方式有get和post两个'>
</form>
```


get和post的区别：
    get是追加到地址栏，post是以http的post机制传输数据。
    get小快不安全。

<!--more-->
**2. 其他标签**

文本输入框  <input type='text'> `<input type='text'>`
密码输入框  <input type='password'> `<input type='password'>`
单选       <input type='radio'> `<input type='radio' name='同一组单选的name值要一致'>`
复选       <input type='checkbox'> `<input type='checkbox' name='同一组复选的name值要一致'>`

提交按钮   <button type='submit'>按钮上的文字</button> `<button type='submit'>按钮上的文字</button>`
重置按钮   <button type='reset'>按钮上的文字</button> `<button type='reset'>按钮上的文字</button>`

```
属性说明：
每一个输入框都必须有name属性。
placeholder属性是设置提示文本的
```
#### css

概念：层叠样式表，在网页实现样式的。
语法：
```
选择器{
    属性：属性值;
    属性：属性值;
}
```

- css的三种引入方式
  - 内联式（行内样式）
    <元素 style=' 属性:属性值;属性：属性值; '></元素>
    ```css
    <p style='color:pink;'>段落文字</p>
    ```

  - 内部式
    1.在head标签里面添加一个style标签
    2.在style里按照css基本语法写代码
    <head>
        ....
        <style>
            选择器{
                属性：属性值;
                属性：属性值;
            }
        </style>
    </head>

  - 外链式
    1. 新建一个以.css为后缀的css文件
    2. 在head里添加link标签，在它的href属性里面写要引入的css文件的路径
    3. 在css文件里按照css基本语法写代码
    4. 
    ```html
    <head>
        ....
        <link rel='stylesheet' href='要引入的css文件的路径'>
    </head>
    
    <div>这是div的内容</div>   给div的文字颜色变成红色，改变字体大小为60
    ```
- 选择器：是一种匹配模式，用于匹配想要选中的元素
  - 基础选择器
    1. 选中所有元素  [通配符]
        *{   }
    
    2. 选中所有对应的标签  【标签选择器】
        标签名{  }
    
    3. 选中所有有对应类名的元素   [类选择器]
        - 元素设置类名    `<元素 class='类名1 类名2'></元素>`
        - 使用类选择器    `.类名1{  }或者 .类名2{  }`
    
    4. 选中指定id名的元素    [id选择器]
        - 元素设置id名    `<元素 id='id名'></元素>`
        - 使用id选择器    `#id名{   }`
    
    5. 群组选择器   
        选中a和b    `a,b{  }`

        **注意：**  id名是唯一的！class是可以重复的
        推荐给页面的大块区域使用id命名，区域里面的元素使用class命名

- 选择器的优先级
    ```
    !important > 行内样式  >  id  > class  > 标签 >*
      无穷        1000       100    10       1     0
    ```
    多个选择器，计算权重之和。大的优先。如果权重一致，后者覆盖前者。

