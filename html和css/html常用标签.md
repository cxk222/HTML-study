---
title: 01-html常用标签
date: 2021-06-20
tags: html
categories: html
---
# HTML常用标签
#### 命名规范
- 命名应该由数字、字母、下划线组成，不能以数字开头
- 最好名字应该是对应内容的英文
- 推荐使用驼峰命名

####  HTML入门
html文件：以.html为后缀的文件  
html:超文本标记语言
超文本：除去文本之外还可以有图片、音频、视频、超链接等
标记：是一种标记符号，形如 `<b></b>`
<!--more-->
1. html文件的基本结构
 ``` html
 <!DOCTYPE html>   声明文档类型是html
<html>     标记文件开始
    <head>   头部
        <meta charset='utf-8'>   语言-编码格式
        <title></title>   网页标题
    </head> 
    <body>  身体-网页内容
    </body>
</html>   标记文件结束
 ```
    
2. 语法
        <元素 属性='属性值' 属性='属性值'>内容</元素>

#### html常用标签
1. 标题  hn  [n代表1-6的数字]
        `<hn>标题</hn>`
2. 段落   p
        `<p></p>`
3. 水平线  hr
        `<hr>`
4. 换行   br
        `<br>`

5. 文字标签
   - 加粗  b  strong
    ```html
     <b>要加粗的内容</b>
     <strong>要加粗的内容</strong>
    ```
    - 倾斜  i  em
    ```html
     <i>内容</i>
     <em>内容</em>
    ```
    - 变大 big
    `<big></big`>
    - 变小 small
    `<small></small>`
    - 上标  sup
    `<sup>上标内容</sup>`
    - 下标  sub
    `<sub>下标内容</sub>`
6. 特殊符号
        &符号名;
        大空格   ` &emsp;`
        版权     `&copy;`
        商标     `&reg;`

7. 列表标签
    - 有序列表
    ```html 
    <ol>
        <li>列表项</li>
    </ol>
     ```
        
    - 无序列表
    ```html
    <ul>
        <li>列表项</li>
    </ul>
     ```   
    - 定义列表（了解）
    ```html 
    <dl>
        <dt>名词、专业术语</dt>
        <dd>对名词或者专业术语的解释说明</dd>
    </dl>
     ```   
8. 图片
```html
    <img src='图片的路径' alt='替代文本' width='宽度' height='高度' title='悬停的提示文本'>
 ```

9. 路径
        1.绝对路径：从协议或者盘符开始的路径。
        2.相对路径：从当前位置出发，得到的路径。
            同级    直呼其名
            下级    /谁
            上级    ../
    
10. 超链接
    ```html
    <a href='要跳转的地址' target='_self 或者 _blank'>要被标记为链接的内容</a>
    ```
        _self是在当前标签页打开新页面
        _blank是在新的标签页打开新页面

11. div标签  块标签:主要用于后期布局实现样式的标签，本身没有任何特殊效果
        `<div></div>`
   
12. 表格
```html
<table border='边框的粗度' cellspacing='0边框之间的间隔' cellpadding='边框和文字之间的间隔'>   表格
    <tr>   行
        <td>单元格的内容</td>
    </tr>
</table>
```
跨行  rowspan
跨列  colspan
语法：  `<td colspan='占据的单元格'></td>`

实现合并单元格的步骤：
1. 判定跨行还是跨列，选择最左上角的单元格，添加对应的属性
2. 属性值应该是占据的单元格数量。保存，看错误效果
3. 给对应行多余的单元格删除 【从后往前删除】
  



    
  



