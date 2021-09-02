---
title: 表单其他标签和属性
date: 2021-07-06
tags: html
categories: html
---

#### 标签语义化
- 概括：语义就是有意义，要用正确的标签描述相应的内容，见名知意
- 好处：
    代码具有可读性
    方便SEO（搜索引擎优化）

- 新增的标签
    |标签|标签名|
    |:---:|:---:|:---:|
    |页头|header|      
    |页脚|footer |  
    |侧栏|aside  | 
    |独立区域块|section|     
    |主体|main|
    |导航|nav|
    |文章|article|

<!--more-->


#### 多媒体标签
- 音频
    ```html
    <audio src='音频的路径' controls   autoplay   loop></audio>
    ``` 
    controls       控件
    autoplay       自动播放
    loop           循环

- 视频
    ```html
    <video src='视频地路径'  controls  poster='海报的路径'>不能识别video标签时候显示的内容</video>
    ```

####  html5新增的type属性值和属性
  - type属性值  ：email  url（网址）  number 
    <br>
  - type新增的属性 ： 
      |属性|属性名|
      |:---:|:---:|
      |验证表单数据的正确性|novalidate(用在form身上，不验证)|
      |必须填内容 |required|
      |提示符 |placeholder|
      |自动获取焦点|autofocus|
      |最大长度|maxlength|
      |自动补全|autocomplete='on'|
    <br>
  - html5新增的标签
     数据列表
      语法：
      ```html
      <input list='id名'>
      <datalist id='id名'>
          <option value=''>内容</option>
      </datalist>
      ```