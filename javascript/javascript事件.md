---
title: javascript事件
date: 2021-08-03
tags: javascript事件
categories: javascript
decription: 
---
## JavaScript事件
#### JavaScript时间简介
事件组成部分：事件源、事件类型、事件处理函数
#### 事件对象event
- 每触发一个事件都会生成事件对象
- 获取事件对象
    ```js
    oDiv.onclick = function(e){
        e = e || window.event
        //e就是事件对象
    }
    ```
<!---more--->
#### 点击事件的光标坐标点
- 相对事件源 offsetX,offsetY
- 相对浏览器窗口 clientX,clientY
- 相对于页面 pageX,pageY
#### 常见的事件
- 浏览器事件
    ```
    load ： 页面全部资源加载完毕
    scroll ： 浏览器滚动的时候触发
    onresize    页面大小事件
    ```

- 鼠标事件
    ```
    click ：点击事件
    dblclick ：双击事件
    contextmenu ： 右键单击事件
    mousedown ：鼠标左键按下事件
    mouseup ：鼠标左键抬起事件
    mousemove ：鼠标移动
    mouseover ：鼠标移入事件
    mouseout ：鼠标移出事件
    mouseenter ：鼠标移入事件
    mouseleave ：鼠标移出事件
    ```
    区块随光标移动案例：
    ```
    思路: 1. 鼠标移入区块显示提示信息
                    mouseover 移入
            2. 鼠标移出区块隐藏提示信息
                    mouseout 移出
            3. 鼠标在区块移动，提示信息跟随移动
                => mousemove 移动
                => 光标的坐标位置
                        => 浏览窗口 e.clientX e.clientY
                        => 事件源元素本事 e.offsetX  e.offsetY
                        => 文档页面 e.pageX  e.pageY

                => 光标实时坐标位置设置给提示信息元素
                
                解决闪烁问题
                => 光标位置与提示信息位置重叠一起， 当光标移入div区块,显示p区域,这时光标相当于落在p区域，
                移出div区块,提示信息隐藏.
                    p{ pointer-events: none;} 光标(鼠标)事件,值设置none之后当前元素事件无效
            4. 元素不能移出div区块
    ```       

- 键盘事件
    ```
    keyup ： 键盘抬起事件
    keydown ： 键盘按下事件
    keypress ： 键盘按下再抬起事件
    .keyCode : 键盘的编码   兼容写法: .which
    组合按键：
    altkey : alt键按下得到true，否则得到false
    shiftKey : shift键按下得到true，否则得到false
    ctrlKey : ctrl键按下得到true，否则得到false
    ```

- 表单事件
    ```
    change : 表单内容改变事件
    input : 表单内容输入事件
    submit : 表单提交事件
    blur : 失去焦点
    focus : 获取焦点
    ```

- 触摸事件
    ```
    touchstart ： 触摸开始事件
    touchend ： 触摸结束事件
    touchmove ： 触摸移动事件
    ```

#### 事件的绑定方式
- **事件属性**
    ``` html
    <!-- 把事件写在标签的属性里 -->
    <input type = "button" onclick = "函数名" value = "按钮">
    ```
- **事件绑定**
  - 优点：符合“行为，样式，结构”相分离；便于操作当事对象；方便读取事件对象
  - 缺点：只能给一个元素注册一个事件，绑定一个事件，后一个会覆盖前一个
    ```js
    oDiv.onclick = function(){
        console.log('我是第一个事件')
    }
    oDiv.onclick = function(){
        console.log('我是第二个事件')
    }
    当进行点击时候，只会执行第二个，第一个会被覆盖
    ```
- **事件监听**
  - addEventListener : 非IE 7 8下使用
  
  ```js
  /* 
  语法：元素.addEventListener('事件类型'，'事件处理函数'，'冒泡还是捕获')
  true:表示注册的事件在捕获阶段触发
  false:表示注册的事件在冒泡阶段触发-----默认值 
  */
    oDiv.addEventListener ('click',function(){
        console.log('我是第一个事件')
    },false)
    oDiv.addEventListener ('click',function(){
        console.log('我是第二个事件')
    })
    //先打印第一个事件，再打印第二个事件
  ``` 
  - attachEvent : IE 7 8下使用 

  ```js
  /* 语法：元素.attachEvent('事件类型'，'事件处理函数') */
    oDiv.attachEvent ('click',function(){
        console.log('我是第一个事件')
    })
    oDiv.attachEvent ('click',function(){
        console.log('我是第二个事件')
    })
    //先打印第二个事件，再打印第一个事件
  ```

  ```
  1.注册事件的时候事件类型参数的书写
    addEventListener : 不用写on
    attachEvent : 要写on
  2.参数个数
    addEventListener : 一般三个常用参数
    attachEvent : 两个参数
  3.执行顺序
    addEventListener : 顺序注册，顺序执行
    attachEvent ： 顺序注册，倒叙执行
  ```
#### 事件的执行机制
- **事件冒泡**
  就是从事件 目标 的事件处理函数开始，依次向外，直到 window 的事件处理函数触发也就是从下向上的执行事件处理函数
- **事件捕获**
  就是从 window 的事件处理函数开始，依次向内，只要事件 目标 的事件处理函数执行也就是从上向下的执行事件处理函数
  [![hP4hQ0.png](https://z3.ax1x.com/2021/08/23/hP4hQ0.png)](https://imgtu.com/i/hP4hQ0)

- **事件目标对象-target**
    target 这个属性是事件对象里面的属性，表示你点击的目标
    当你触发点击事件的时候，你点击在哪个元素上，target 就是哪个元素
    这个 target 也不兼容，在 IE 下要使用 srcElement

- **事件委托**
    ```html
    <ul>
        <li class="l1">元素一</li>
        <li class="l2">元素二</li>
        <li class="l3">元素三</li>
    </ul>

    <script>
        var ulEle = document.querySelector('ul')
        ulEle.addEventListener('click',function(e){
            e = e || window.event // 事件对象
            var target = e.target || e.srcElement // 事件目标对象
            var classValue = target.getAttribute('class')
            if(classValue == 'l1'){
                console.log("收元素一 的包裹")
            }else if( classValue == 'l2'){
                console.log("收元素二 的包裹")
            }else if( classValue == 'l3'){
                console.log("收元素三 的包裹")
            } 
        })

    </script>
    ```
#### 默认行为
```
默认行为，就是不用我们注册，它自己就存在的事情
比如我们点击鼠标右键的时候，会自动弹出一个菜单
比如我们点击 a 标签的时候，我们不需要注册点击事件，他自己就会跳转页面
...
这些不需要我们注册就能实现的事情，我们叫做 默认事件
```
- 阻止默认事件：
e.preventDefault() : 非 IE 使用    
e.returnValue = false ：IE 使用

```html
<a href = "https://www.baidu.com">点击我</a>
<script>
    var oA = document.querySelector('a')
    oA.addEventListener('click',function(e){
        e = e || window.event
        console.log(this.href)
        e.preventDefault ? e.preventDefault() : e.returnValue = false
    })
    // 点击a标签时候不会跳转链接，只会在控制台打印出a标签的href属性的值
</script>
```