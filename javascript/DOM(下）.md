---
title: 10-DOM（下）
date: 2021-08-02
tags: BOM
categories: javascript
decription: 
---

[![f8T4fI.png](https://z3.ax1x.com/2021/08/09/f8T4fI.png)](https://imgtu.com/i/f8T4fI)
<!--less-->


### DOM节点

#### DOM节点分类
- DOM节点类型
    - 整个文档是一个文档节点
    - 每个HTML元素时元素节点
    - HTML元素内的文本是文本节点
    - 每个HTML属性是属性节点
    - 注释是注释节点

- 常用的三大类：元素节点/文本节点/属性节点
    - 元素节点：通过getElementBy...获取
    - 属性节点：通过getAttribute获取
    - 文本节点：通过innerText获取
- DOM节点树形结构
[![f8T4fI.png](https://z3.ax1x.com/2021/08/09/f8T4fI.png)](https://imgtu.com/i/f8T4fI)
- DOM节点关系
    - 根节点： 在HTML文档中，html就是根节点。
    - 父节点： 一个节点之上的节点就是该节点的父节点，例如ul的父节点就是body，body的父节点就是html。
    - 子节点： 一个节点之下的节点就是该节点的子节点，例如ul就是body的子节点。
    - 兄弟节点： 如果多个节点在同一层次，并拥有相同的父节点，那么这几个节点就是兄弟节点。
  
#### 获取节点
- 获取元素节点
    - getElement系列
    - querySelector系列
- 层次关系获取节点

  |      属性       |                                    说明                                    |
  | :-------------: | :------------------------------------------------------------------------: |
  |   parentNode    |               获取所选节点的父节点，最顶层的节点为#document                |
  |   childNodes    |                           获取所选节点的子节点们                           |
  |   firstChild    |                         获取所选节点的第一个子节点                         |
  |    lastChild    |                        获取所选节点的最后一个子节点                        |
  |   nextSibling   | 获取所选节点的后一个兄弟节点  列表中最后一个节点的nextSibling属性值为null  |
  | previousSibling | 获取所选节点的前一兄弟节点   列表中第一个节点的previousSibling属性值为null |


- 层次关系获取元素节点

    |          属性          |                    说明                     |
    | :--------------------: | :-----------------------------------------: |
    |     parentElement      |  返回当前元素的父元素节点（IE9以下不兼容）  |
    |        children        |          返回当前元素的元素子节点           |
    |   firstElementChild    |  返回的是第一个元素子节点（IE9以下不兼容）  |
    |    lastElementChild    | 返回的是最后一个元素子节点（IE9以下不兼容） |
    |   nextElementSibling   | 返回的是后一个兄弟元素节点（IE9以下不兼容） |
    | previousElementSibling | 返回的是前一个兄弟元素节点（IE9以下不兼容） |

- 获取元素节点的所有属性节点：attributes
- 非常规节点获取
    html根节点: document.documentElement
    body节点: document.body
    head: document.head

#### 节点属性
| 节点类型 | nodeType |  nodeName  | nodeValue |
| :------: | :------: | :--------: | :-------: |
| 元素节点 |    1     | 大写标签名 |   null    |
| 属性节点 |    2     |   属性名   |  属性值   |
| 文本节点 |    3     |   #text    | 文本内容  |

#### 操作DOM节点
- 创建节点
  - `createElement`:用于创建一个元素节点
    ```js
    var oDiv = document.createElement('div')
    console.log(oDiv) // <div></div>
    ```
    `creatTextNode`:用于创建一个文本节点
    ```js
    var oText = document.creatTextNode('我是一个文本')
    console.log(oText) // '我是一个文本'
- 加入节点
    - `appendChild`:向一个元素节点的末尾追加一个节点
    ```js
    var oDiv = document.createElement('div')
    var oText = document.createTextNode('我是一个文本')
    //向div中追加一个文本节点
    oDiv.appendChild(oText)
    console.log(oDiv) // <div>我是一个文本</div>
    ```
    - `insertBefore`:向某一个节点前插入一个节点
    ```js
     <div>
        <li></li>
        <li></li>
    </div>
    <script>
        var oDiv = document.querySelector('div')
        var oP = document.createElement('p')
        oDiv.insertBefore(oP, oDiv.firstElementChild)
    </script>
    /*  <div>
            <p></p>
            <li></li>
            <li></li>
        </div>
    */ 
    </div>
    ```
- 删除节点
- 修改节点
 