### 1. 两种盒子模型
> 区别：

（1） 标准盒子模型：width = content

（2） IE盒子模型：width = content + padding + border

> 设置：

（1）标准盒子模型：box-sizing: content-box;

（2）IE盒子模型：box-sizing: border-box;

### 2. CSS选择器有哪些？优先级如何计算？

（1） id选择器(#myid)
（2） 类选择器(.myclassname)
（3） 标签选择器(div, h1, p)
（4） 子选择器（ul > li）
（5） 伪类选择器（a:hover, li:nth-child）

> 优先级（就近原则）：!important > 内联元素 >  id > class > tag 

### 3.position 有哪些值？

（1） static（默认）：按照正常文档流进行排列；

（2） relative（相对定位）：不脱离文档流，参考自身静态位置定位；

（3） absolute(绝对定位)：参考距其最近一个不为static的父级元素定位；

（4） fixed(固定定位)：所固定的参照对像是可视窗口。

### 4. display: none 与visibility：hidden 和 opacity : 0的优缺点和适用场景？

（1） display：none 不显示对应的元素，在文档布局中不再分配空间（回流+重绘），可以理解成在页面中把该元素删除掉一样。

（2） visibility：hidden 隐藏对应元素，在文档布局中仍保留原来的空间（重绘），但是不会触发该元素已经绑定的事件

（3） opacity : 0，该元素隐藏起来了，但不会改变页面布局，并且，如果该元素已经绑定一些事件，如click事件，那么点击该区域，也能触发点击事件

> 结构

display：none会让元素从渲染树中消失，渲染的时候不占据任何空间，不能点击；visibility：hidden，渲染元素会继续占据空间，只是不可见，不能点击；opacity: 0，渲染元素继续占据空间，只是不可见，可以点击

> 继承 

display: none是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示。 visibility: hidden：是继承属性，子孙节点消失由于继承了hidden，通过设置visibility: visible;可以让子孙节点显式。opacity: 0也是继承元素，父节点设置opacity之后，子元素在设置一个opacity，那么子元素的效果是两者的乘积

> 性能

displaynone : 修改元素会造成文档回流,读屏器不会读取display: none元素内容，性能消耗较大 visibility:hidden: 修改元素只会造成本元素的重绘,性能消耗较少读屏器读取visibility: hidden元素内容 opacity: 0 ： 修改元素会造成重绘，性能消耗较少

### 5. 对 BFC 的理解

> BFC（块级格式化上下文）是一块独立的渲染区域，相当于一个独立的容器，里面的元素和外面的元素互不影响

* 特点

（1）内部的box会在垂直方向上一个接一个的放置

（2）同一个BFC内的两个box的margin会发生重叠

（3）BFC的区域不会和float box重叠

（4）在BFC中，每一个盒子的margin-left会触碰到容器的border-left

（5）计算BFC的高度时，浮动元素也会参与计算

* 创建方式

（1）HTML根元素

（2）float的值不为none

（3）overflow的值不为visible

（4）display为表格布局或者弹性布局或者inline-block

（5）position为absolute或者fixed

* 作用

1. 清除浮动造成的父级高度塌陷

2. 防止外边距重叠

### 6. 怎么让一个 div 水平垂直居中

``` css
// 1. flex布局
.parent {
  display: flex;
  align-items: center;
  justify-content: center;
}

// 或者
.parent {
  display: flex;
}

.child {
  margin: auto;
}

// 2. 绝对定位
.parent {
  position: relative;
}

.child1 {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}

.child2 {
  width: 100px;
  height: 50px;
  position: absolute;
  left: 50%;
  top: 50%;
  margin-left: -50px;
  margin-top: -25px;
}

.child3 {
  width: 100px;
  height: 50px;
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
}

// 3. grid布局
.parent {
  display: grid;
}
.child{
  justify-self: center;
  align-self: center;
}

```

### 7. 实现多行文本溢出省略效果
```css
// 1. 单行
{
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
// 2. 多行
{
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3; //行数
  overflow: hidden;
}
```