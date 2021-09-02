---
title: CSS核心属性
date: 2021-06-25
tags: 
- css
- css核心属性
categories: - css
---

## CSS核心属性
#### 一、文本属性
1. 字体大小——font-size:  ;
    ```txt
    单位：px  像素
          em  基于父级的倍数
          rem 基于根目录（html）的倍数
    ```
2. 颜色color
    ```txt
    颜色的英文/#16进制值/rgb(R,G,B)/rgba(R,G,B,透明度)
    ```
3. 文字粗细
    ```css
    font-weight:400/normal|700/bold;
    ```
<!--more-->
4. 字体类型
    ```css
    font-family:'';
    ```
5. 字体样式
    ```css
    font-style:noraml/italic;
    ```
6. 行高
    ```css
    line-height:*px;
    ```
7. 文字水平对齐
    ```css
    text-align:center/left/right/justify(两端对齐)
    ```
8. 文本缩进
    ```css
    text-indent:  行级元素不生效
    ```
9. 修饰线
    ```css
    text-decoration:underline(下划线)/line-through(删除线)/none(用于去除链接下划线);
    ```
10. font复合属性
    ``` css
    font:font-style font-weight font-size/line-height font-family; 
    ```
    最少要写字体大小和类型
11. 字间距
    ```css
    letter-spacing:
    ```


#### 二、列表属性
```css
list-style:none; 去掉序列的样式
```


#### 三、继承
有上下级关系的元素之间，上级元素的样式被下级拥有


#### 四、背景属性
1. 背景颜色 background-color 
2. 背景图片 background-image:url( );
3. 背景平铺 background-repeat:no-repeat/repeat/repeat-X/repeat-Y;
4. 背景起始位置 background-position:x坐标 y坐标；（居中 background-position:center center;)
5. 背景图片的固定 background-attachment：scroll(滚动）/fixed（固定）
6. 背景图片的大小 background-size：宽度 高度；

#### 五、精灵图
1. 实现一个指定大小的盒子
2. 设置精灵图为背景图
3. 通过background-position来调整背景图的位置

优缺点： 性能好，命名少，步骤繁琐，增添图标麻烦